# sunworks

일상의 작은 발견을 직접 쓰고 싶은 앱과 웹서비스로 만드는 sunworks의 회사 소개 사이트.

- 사이트: https://www.sunworks.kr
- 소스: https://github.com/sunworks-dev/sunworks-website
- 기반: Astro, TypeScript, CSS, Canvas PNG 내보내기
- 브랜드: 사용자 제공 한글 로고, 노랑–주황 그라데이션, 빈티지 인쇄풍 일러스트
- 언어: 한국어 `/`, 영어 `/en/`. 두 언어 문구는 `src/i18n.ts`에서 관리
- 체험: 딴생각 카드 넘기기와 1080×1350 PNG 저장 (별도 API 없음)
- 배포: Cloudflare Pages, GitHub Actions

## 개발

Node.js 24 LTS 권장. `.nvmrc`를 제공합니다.

```sh
npm ci
npm run dev
```

개발 서버는 http://localhost:4321 에서 실행됩니다.

```sh
npm run verify  # 형식, 타입, 프로덕션 빌드
npm run preview
```

## 배포

`main`에 푸시하면 검사 통과 후 `wrangler pages deploy`로 `dist/`를 Cloudflare Pages(`sunworks-website` 프로젝트)에 배포합니다. PR에서는 검사만 실행합니다.
배포에는 저장소 secret `CLOUDFLARE_API_TOKEN`(Pages 편집 권한만)과 `CLOUDFLARE_ACCOUNT_ID`가 필요합니다.
도메인 DNS는 Cloudflare에서 관리합니다. `www.sunworks.kr`은 Pages 커스텀 도메인이고, `sunworks.kr`은 Cloudflare 리디렉트 규칙으로 `www`로 이동합니다.

## 프로젝트 문서

- [제품과 콘텐츠 기준](docs/PRODUCT.md)
- [디자인 시스템](docs/DESIGN.md)
- [백엔드 확장](docs/architecture.md)
- [배포와 도메인](docs/launch.md)

## 공개 범위

공개 저장소이며 npm 패키지로 배포하지 않습니다. 오픈소스 재사용 라이선스는 아직 지정하지 않았습니다.
비밀키, 환경 변수의 실제 값, 개인정보를 커밋하지 마세요. 외부 폰트 라이선스는 해당 자산과 함께 보관합니다.
