# 🥶 Playwright

## E2E(End to End) Test

애플리케이션을 전체적으로 테스트하는 것으로, 사용자가 실제로 수행하는 작업을 흉내내어 애플리케이션의 모든 구성 요소가 올바르게 상호 작용하고 예상대로 작동 하는지를 확인한다.\
예를 들어, **웹 애플리케이션의 E2E 테스트는 사용자가 페이지를 방문하고 버튼을 클릭하며 폼을 제출하는 등의 행동을 수행하여 애플리케이션의 모든 기능을 테스트**합니다.

### E2E(End to End) Test 장점&#x20;

* 애플리케이션의 실제 동작을 더 잘 반영 하므로, 더 높은 품질의 테스트를 제공한다.&#x20;
* 사용자 관점에서 테스트가 가능하다.
* 애플리케이션의 모든 부분을 테스트 하기 때문에, 프로덕션 환경에서 발생할 수 있는 문제를 사전에 파악할 수 있다.

## Headless Chrome

화면에 창을 표시하지 않고 백그라운드에서 브라우저를 실행할 수 있도록 하며 **웹스크래핑, 자동화된 테스트 및 웹 페이지의 서버 측 렌더링과 같은 다양한 작업에 유용**하다.

## Puppeteer

[puppeteer](https://developer.chrome.com/docs/puppeteer/overview/)

구글에서 개발한 **Node.js 라이브러리**로 **Headless Chrome** 브라우저를 사용하여 웹 스크래핑, 자동화 테스트 등의 작업이 가능하며 **Chrome DevTools Protocol**을 사용하여 Chrome 브라우저를 제어하고, 브라우저에서 실행되는 JavaScript 코드를 실행하고, DOM(Document Object Model)을 조작하고, 네트워크 요청을 가로채고 수정할 수 있습니다.



## Playwright

[Playwright](https://playwright.dev/)\
[Playwright Configuration](https://playwright.dev/docs/test-configuration)\
[Ashal의 Playwright](https://github.com/ahastudio/til/blob/main/test/playwright.md)

**웹 브라우저 기반 E2E 테스트 자동화 도구**, 즉 개발자가 웹 브라우저의 사용자 상호작용을 자동화 할 수 있게 해주는 오픈소스 Node.js 라이브러리이며 Headless Chrome을 기반이다. Puppeteer와 유사한 API를 가지고 있으며, Puppeteer와 비교하여 더 다양한 기능과 성능 향상을 제공한다.

### Playwright 패키지 설치 및 사용법

```bash
npm i -D @playwright/test eslint-plugin-playwright
```

`playwright.config.ts` 파일

```jsx
import { PlaywrightTestConfig } from '@playwright/test';

const config: PlaywrightTestConfig = {
	testDir: './tests',
	retries: 0,
	use: {
		baseURL: '<http://localhost:8080>',
		headless: !!process.env.CI,
		screenshot: 'only-on-failure',
	},
};

export default config;
```

`tests/.eslintrc.js` 파일

```jsx
module.exports = {
	env: {
		jest: false,
	},
	extends: ['plugin:playwright/playwright-test'],
	rules: {
		'import/no-extraneous-dependencies': 'off',
	},
};
```

`tests/home.spec.ts`

```jsx
import { test, expect } from '@playwright/test';

test('Filter products', async ({ page }) => {
	await page.goto('/');

	await expect(page.getByText('Apple')).toBeVisible();

	const searchInput = page.getByLabel('Search');

	await searchInput.fill('a');

	await expect(page.getByText('Apple')).toBeVisible();

	await searchInput.fill('aa');

	await expect(page.getByText('Apple')).toBeHidden();
});

test('Click the “Increase” button', async ({ page }) => {
	await page.goto('/');

	const count = 13;

	await Promise.all((
		[...Array(count)].map(async () => {
			await page.getByText('Increase').click();
		})
	));

	await expect(page.getByText(`${count}`)).toBeVisible();
});
```

테스트 실행

```bash
npx playwright test
```

`.gitignore` 파일에 에러 상황의 스크린샷 등이 담기는 `test-results` 디렉터리 추가.

* 웹 브라우저 기반 E2E 테스트 자동화 도구&#x20;
* CodeceptJS
