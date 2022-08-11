# 목적

더 편하게 확인 할 수 있는 next.js navigation guard 만들기

# 기존 문제점

next.js는 pages 폴더 안에 바로 path가 매핑되는 구조이다.
기존의 vue, react는 routes를 관리하는 파일이 있어, 거기서 쉽게 route navigation 설정이 가능하다.
한편, next.js는 그렇게 하지 못하기 때문에,
단순하게 getStaticProps를 이용하는 등으로 page 별로 처리를 할 수 있다.

이렇게 할 경우, 매 페이지마다 getStaticProps를 선언해야 하는 불필요함과
페이지 별 접근 권한 변경 시, 고치기가 불편할 수 있다.

# 해결 방향

hoc 구조로 각 page에 접근할 때마다 먼저 page에 대한 guard 처리할 middleware를 만든다.
