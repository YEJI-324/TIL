# assets vs static

정적파일을 assets이나 static 폴더에 저장.

## :one: assets
[공식문서](https://nuxtjs.org/docs/directory-structure/assets/)
- Webpack loader → 번들링 처리.
- Vue 파일에 추가한 상대 경로를 통해 로더는 파일 이름 및 식별자, 조건 처리된 base64 인코딩 처리된 코드를 사용할 수 있도록 처리.
- 처리된 assets은 소스코드. 빌드되는 동안 인라인/복사/이름변경 가능.

:point_right: Webpack이 처리할 정적 자원을 ./src 디렉토리 내에 포함하는 것 권장.

## :two: static
[공식문서](https://nuxtjs.org/docs/directory-structure/static)
- Webpack loader에 의해 처리되지 않음.
- 내부파일은 최종 결과에 직접 복사됨.
- Nuxt가 루트로 매핑해줌. → '/'으로 접근가능.

:point_right: 변경되지 않거나 번들링이 필요없는 정적파일을 ./static 디렉토리 내에 포함하는 것 권장.

<br>

> ## 📝 webpack
> - javascript 애플리케이션을 위한 module bundler
> - 애플리케이션에 필요한 모든 파일(모듈)을 병합하고 압축해서 하나의 결과물(번들)을 생성해주는 도구 → 애플리케이션의 성능 및 로드 시간을 줄여주는 역할


<br>


### ref
https://stackoverflow.com/questions/48808182/nuxt-assets-and-static-folder-when-to-use-which
