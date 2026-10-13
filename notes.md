# 컴퓨터 보안 졸업고사 — Docs 기반 문제번호별 정리

이 문서는 시험범위 탭에서 '-'로 시작하는 문단의 순서대로 1~24번을 정리한 자료입니다. 본문과 코드 예시는 아래 Docs의 시험범위·수업 탭을 바탕으로 정리했습니다.

**읽는 기준**

- **Docs 시험 힌트:** 시험범위에 제시된 질문·주제입니다.
- **Docs 수업 내용:** 수업 문서에서 확인한 내용과 예시입니다. 문장을 요약하고 코드의 줄바꿈·Markdown 표시를 정리했습니다.
- **원문 확인 필요:** 문서에 정답이 없거나 예시가 모순되는 부분입니다. 확정 정답으로 암기하지 않습니다.
- **이해 도움 — 추가 설명(시험 정답 아님):** 제가 덧붙인 설명입니다. 시험 답이나 퀴즈의 채점 조건이 아닙니다.

## 출처

- [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr)
- [웹 해킹 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9)
- [리눅스 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.6w305jslelsk)
- [SQL Injection](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.8dro0sijblpf)
- [SQL Injection 마무리](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ljvdeb9idd4h)
- [2학기 수행 기초 — 모의해킹 사이트 만들기](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ant3m5zchvie)
- [2학기 수행 기초2 — 모의해킹 사이트 만들기](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.r1pyvza0s9g5)

## 1번. 우클릭 차단 우회

**Docs 시험 힌트:** 특정 웹사이트에서 우클릭이 막혔을 때 해결할 수 있는 방법은?

**Docs 수업 내용**

시험범위에는 다음 다섯 방법이 나옵니다.

1. F12로 개발자 도구를 열어 소스코드 보기.
2. 개발자 도구에서 해당 페이지의 JavaScript 비활성화.
3. 개발자 도구에서 document.body 직접 출력.
4. Chrome 주소창에서 view-source:url 방식으로 접속.
5. curl 같은 텍스트 기반 도구로 웹에 직접 접속.

수업 탭에서는 Elements에서 확인, HTML 저장 후 텍스트로 확인, Event Listeners에서 이벤트 제거, 소스 수정·override 등의 방법도 다룹니다. Console에서 다룬 표현은 다음과 같습니다.

~~~javascript
document.body
document.body.oncontextmenu=null
~~~

**정답 표현 기준:** 직접 출력하는 답은 document.body입니다. document.body.outerHTML은 Docs에 없는 표현이므로 답으로 요구하거나 정답으로 채점하지 않습니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [웹 해킹 기초 — natas1](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9)

## 2번. 개발자 도구

**Docs 시험 힌트:** 웹 브라우저나 소프트웨어에 내장되어 개발자가 코드를 검사·수정·테스트·디버깅할 수 있도록 돕는 도구는?

**Docs 수업 내용**

수업에서 F12로 열어 소스·이벤트·쿠키·요청 등을 확인하는 도구는 **개발자 도구**입니다. 1번의 소스 확인과 4번의 영역 구분을 함께 복습합니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [웹 해킹 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9)

## 3번. Curl·SSHD·Apache·Chrome·Event Listener 구분

**Docs 시험 힌트:** Curl, SSHD, Apache, Chrome, Event Listener 구분.

**Docs 수업 내용**

| 용어 | 문서에서 확인한 사용 장면 |
| --- | --- |
| curl | 텍스트 기반 도구로 웹에 접속해 응답 확인 |
| Apache | 웹서버 실행 및 웹루트 설정 |
| Chrome | 브라우저에서 페이지·소스·개발자 도구 확인 |
| Event Listener | 우클릭 차단과 관련된 이벤트를 확인·제거 |
| SSHD | 시험범위에 이름이 등장함 |

Apache 수업에서는 웹루트를 C:\web으로 두고 URL과 로컬 파일의 연결을 설명합니다. 디렉터리의 파일 목록 노출에 대해서는 디렉터리 목록 기능을 끄거나 index.html을 두는 방법이 나옵니다.

**원문 확인 필요:** SSHD의 정의를 확정하는 설명은 확인한 수업 텍스트에 없습니다. 24번의 ssh 접속 명령을 SSHD의 정의 대신 외우지는 않습니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [웹 해킹 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9)

## 4번. 개발자 도구의 영역

**Docs 시험 힌트:** 개발자 도구의 영역 구분.

**Docs 수업 내용**

| 영역·기능 | 수업에서 수행한 작업 |
| --- | --- |
| Elements | 페이지 소스 확인·수정 |
| Console | document.body 출력 및 우클릭 이벤트 관련 표현 입력 |
| Event Listeners | 이벤트 확인·제거 |
| Application | Cookie 값 확인·변조 |
| 요청·응답 확인 화면 | GET·POST 데이터 및 HTTP 헤더 비교 |

수업에서 실제로 사용한 영역과 작업을 연결해 복습합니다.

**원문 확인 필요:** 문서에 없는 개발자 도구 탭의 정의를 추가 정답으로 확장하지 않습니다.

출처: [웹 해킹 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9)

## 5번. ARP·Router·Burp Suite·Database·Cookie 구분

**Docs 시험 힌트:** ARP, Router, Burp Suite, Database, Cookie 구분.

**Docs 수업 내용**

| 용어 | 문서에서 확인한 사용 장면 |
| --- | --- |
| Burp Suite | 프록시를 이용해 요청을 확인하고 Referer를 변경하는 실습 |
| Database | SQL 쿼리로 테이블의 정보를 조회하는 실습 |
| Cookie | Application에서 값을 확인·변조하는 natas5 실습 |
| ARP | 시험범위에 이름이 등장함 |
| Router | 시험범위에 이름이 등장함 |

Cookie 수업에서는 PC에 저장된 쿠키 값과 SQLite로 확인하는 과정을 다룹니다.

**원문 확인 필요:** ARP와 Router의 정의는 확인한 수업 텍스트에서 찾지 못했습니다. 임의의 정의를 본문의 정답에 추가하지 않습니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [웹 해킹 기초 — natas4·5](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9), [SQL Injection](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.8dro0sijblpf)

## 6번. 방화벽·프록시 등 구분

**Docs 시험 힌트:** 방화벽, 프록시, C&C 서버, 로그 생성기, DDoS 탐지기 구분.

**Docs 수업 내용**

- **프록시:** natas4에서 Burp Suite를 사용해 Referer를 바꾸는 실습에 등장합니다. 수업에는 Firefox, Chrome ModHeader, curl을 이용하는 방법도 나옵니다.
- **방화벽:** Flask 웹서버의 외부 접속을 위해 인바운드 8000번 포트를 허용하는 과정에 등장합니다. 두 번째 Flask 수업에서는 DB 접속과 관련한 방화벽 설정도 확인합니다.

**원문 확인 필요:** C&C 서버·로그 생성기·DDoS 탐지기는 시험범위에 이름이 있지만, 확인한 수업 텍스트에서 정의·정답 설명을 찾지 못했습니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [웹 해킹 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9), [2학기 수행 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ant3m5zchvie)

## 7번. 리눅스의 텍스트 기반 사용자 인터페이스

**Docs 시험 힌트:** 텍스트 기반 명령어를 통해 컴퓨터를 제어할 수 있는 리눅스 사용자 인터페이스는?

**Docs 수업 내용**

리눅스 수업에서는 ssh로 접속해 ls, cd, find 등의 명령을 입력합니다.

**원문 확인 필요:** 질문에 대한 정답 명칭이 확인한 문서에 직접 제시되어 있지 않습니다. CLI·터미널·셸 중 하나를 제가 골라 확정 정답으로 추가하지 않습니다. 암기 웹페이지에서도 이 번호는 비채점 확인 항목입니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [리눅스 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.6w305jslelsk)

## 8번. 검색엔진 검색 방지

**Docs 시험 힌트:** 검색엔진이 내 사이트를 검색하지 못하게 하고 싶다. 어떻게 하는가?

**Docs 수업 내용**

- robots.txt에서 크롤러가 접근할 경로를 Allow·Disallow로 지정하는 내용을 다룹니다.
- HTML의 head에 아래 메타 태그를 넣는 방법이 나옵니다.

~~~html
<meta name="robots" content="noindex, nofollow">
~~~

natas3에서는 robots.txt에 적힌 경로를 확인하는 과정이 문제 해결의 단서가 됩니다. 수업에서는 실제로 접근을 막으려면 접근 제한을 별도로 해야 한다고 설명합니다.

출처: [웹 해킹 기초 — natas3](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9)

## 9번. Python 외부 패키지 설치

**Docs 시험 힌트:** 파이썬에서 외부 패키지를 다운로드하는 법.

**Docs 수업 내용**

~~~powershell
pip install requests
pip install flask
~~~

requests 수업에서는 requests.get, HTTPBasicAuth, headers 인자, response.text 등을 사용합니다. Flask 수업에서는 설치 후 app.py로 서버를 실행합니다.

**정답 표현 기준:** 수업의 pip install 형태를 기준으로 합니다. 문서에 없는 다른 실행 표현을 별도 정답 조건으로 추가하지 않습니다.

출처: [웹 해킹 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9), [2학기 수행 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ant3m5zchvie)

## 10번. HTTP 응답 코드

**Docs 시험 힌트:** 400번대는 클라이언트 에러, 500번대는 서버 에러, 200번대는 정상 응답.

**Docs 수업 내용**

| 범위 | 시험범위의 구분 |
| --- | --- |
| 2xx | 정상 응답 |
| 4xx | 클라이언트 에러 |
| 5xx | 서버 에러 |

수업에서는 요청 헤더가 잘못됐을 때의 400과, index-source.html에 PUT으로 요청했을 때의 405 Method Not Allowed를 확인합니다.

GET과 POST 비교에서는 다음 내용을 다룹니다.

- GET 데이터는 URL의 Query String Parameters로 확인합니다.
- POST 데이터는 Form Data로 확인합니다.
- PHP에서는 각각 $_GET, $_POST에 데이터가 저장됩니다.
- 수업의 POST 요청 헤더에는 다음 값이 들어갑니다.

~~~http
Content-Type: application/x-www-form-urlencoded
~~~

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [웹 해킹 기초 — natas6](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9)

## 11번. 리눅스 계정정보 확인

**Docs 시험 힌트:** 리눅스 계정정보 확인.

**Docs 수업 내용**

시험범위에 제시된 명령과 출력 예시입니다.

~~~text
user@NCF27:~$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
user:x:1000:1000:,,,:/home/user:/bin/bash
test1:x:1001:1001::/home/test1:/bin/sh
user@NCF27:~$
~~~

확인할 명령은 cat /etc/passwd입니다. 제시된 줄에는 root·user·test1과 /root·/home/user·/home/test1, /bin/bash·/bin/sh가 나옵니다.

**원문 확인 필요:** 이 예시에 없는 계정 파일이나 필드의 별도 정의는 추가 정답으로 요구하지 않습니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr)

## 12번. natas8 — PHP 역산

**Docs 시험 힌트:** natas8이 시험에 나옴. PHP로 코드 역산 작성.

**Docs 수업 내용**

수업의 인코딩 순서는 다음과 같습니다.

~~~php
bin2hex(strrev(base64_encode($secret)))
~~~

수업에서 제시한 값입니다.

~~~php
$secret = "oubWYf2kBq";
$encodedSecret = "3d3d516343746d4d6d6c315669563362";
~~~

역산은 바깥 함수부터 되돌립니다.

| 인코딩 함수 | 역산 함수 |
| --- | --- |
| bin2hex | hex2bin |
| strrev | strrev |
| base64_encode | base64_decode |

수업의 단계별 역산 코드입니다.

~~~php
$b1 = hex2bin($encodedSecret);
$b2 = strrev($b1);
$b3 = base64_decode($b2);
~~~

수업에는 한 줄로 표현하는 코드도 나옵니다.

~~~php
print(base64_decode(strrev(hex2bin("3d3d516343746d4d6d6c315669563362"))));
~~~

> **이해 도움 — 추가 설명(시험 정답 아님):** 인코딩이 Base64 → 뒤집기 → 16진수 변환이라면, 복원은 16진수 복원 → 뒤집기 → Base64 디코딩으로 읽으면 됩니다.

**원문 확인 필요:** 단계별 코드의 최종값은 $b3인데, 원문 일부 출력 코드에는 정의되지 않은 $result가 등장합니다. 이 변수명 불일치는 정답으로 외우지 않습니다.

출처: [웹 해킹 기초 — natas8](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9), [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr)

## 13번. Base64 인코딩의 특징

**Docs 시험 힌트:** Base64 인코딩의 특징.

**Docs 수업 내용**

- 64개의 문자로 표현합니다.
- 알파벳·숫자·+·/로 구성됩니다.
- 원래 데이터를 3바이트 단위로 묶어 표현합니다.
- 나누어떨어지지 않는 경우 끝부분에 = 패딩이 사용됩니다.
- 인코딩은 표현 방식이며 디코딩할 수 있습니다. **Base64는 암호화가 아닙니다.**
- 이메일이나 HTML에서 첨부파일의 내용을 Base64로 직접 표현·전달할 수 있습니다.

12번의 base64_encode와 base64_decode를 함께 복습합니다.

**정답 표현 기준:** 원문에서 다루지 않은 패딩 개수 계산 문제나 추가 규칙을 정답 조건으로 넣지 않습니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr)

## 14번. 리눅스 기본 명령어 — ls

**Docs 시험 힌트:** 리눅스 기본 명령어 사용법.

**Docs 수업 내용**

시험범위의 명령 목록입니다.

~~~bash
ls
ls -a
ls -a -l
ls -al
ls --help
ls --all -h -l
ls -alh /etc/passwd
~~~

리눅스 수업에서는 ls로 파일 목록을 확인하고, ls -a로 숨김 파일을 포함해 확인합니다. ls -al과 ls -a -l은 같은 형태로 설명합니다. 점으로 시작하는 파일과 홈을 뜻하는 ~도 다룹니다.

~~~bash
cd ..
~~~

수업에는 상위 디렉터리로 이동하는 cd ..도 나옵니다.

> **이해 도움 — 추가 설명(시험 정답 아님):** -l은 자세한 목록, -h는 크기를 읽기 쉬운 단위로 표시하는 옵션입니다. 시험범위에는 이 옵션을 포함한 명령이 제시되어 있지만, 이 문장은 옵션을 이해하도록 덧붙인 설명입니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [리눅스 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.6w305jslelsk)

## 15번. find·오류 출력·후속 명령

**Docs 시험 힌트:** find의 경로·크기·파일 종류 옵션과 오류 처리, -exec 사용법.

**Docs 수업 내용**

기본 형태입니다.

~~~bash
find [경로] [옵션] [후속액션]
~~~

시험범위에서 특히 제시한 명령입니다.

~~~bash
find /proc -size -1k -type d -print
find /proc -size -1k -type d -print 2>/dev/null
find /proc -size -1k -type d -exec ls -al {} \;
~~~

- -size: 크기 조건. 수업 예시에는 1033c, +100M 등이 나옵니다.
- -type: 파일 종류 조건. 수업 예시에는 d와 f가 나옵니다.
- 2>/dev/null: 오류 출력을 숨기는 데 사용합니다.
- -exec: 검색된 대상에 후속 명령을 실행합니다. 수업에서 ls·cat·file 등을 사용합니다.

수업의 추가 예시입니다. Markdown 내 역슬래시 이스케이프와 줄바꿈을 명령 표시로 정리했습니다.

~~~bash
find /etc/ -size +100M -print
find ~/inhere ! -executable -print
find ./inhere -size 1033c ! -executable -readable -print -exec cat {} \;
find ~/inhere -type f -print 2>/dev/null
find ~/inhere -type f 2>/dev/null -exec file {} \; | grep ASCII
~~~

수업에서는 문제의 human-readable과 find의 -readable을 구분하고, file 결과와 grep ASCII를 이용하는 과정을 설명합니다. 파이프 |로 앞 명령의 결과를 다음 명령에 연결하는 것도 다룹니다.

웹 수업의 natas9에는 오류를 함께 확인하는 2>&1이 나옵니다. 권한 때문에 읽지 못하는 경우와 파일이 없는 경우를 구분합니다.

> **이해 도움 — 추가 설명(시험 정답 아님):** 2>/dev/null은 오류를 버리는 표현이고 2>&1은 오류를 일반 출력 쪽으로 합치는 표현입니다. {}는 찾은 대상이 들어갈 자리이며 \;는 -exec의 명령 끝을 나타냅니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [리눅스 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.6w305jslelsk), [웹 해킹 기초 — natas9](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.em7tx4gle6r9)

## 16번. SQL Injection — 조건을 참으로 만들기

**Docs 시험 힌트:** SQL 인젝션의 핵심은 항상 진리(참)인 명제로 만드는 것.

**Docs 수업 내용**

수업에서는 사용자 입력이 SQL 문자열에 연결될 때 조건을 바꾸는 과정을 다룹니다. PHP 문자열 연결 연산자인 .도 함께 설명합니다.

조건 예시입니다.

~~~sql
id='admin' and pw='1234' or '1'='1'
~~~

수업에서는 AND가 먼저 계산되는 것으로 설명합니다.

~~~text
(T AND F) OR T
= F OR T
= T
~~~

'1'='1'처럼 항상 참인 조건을 OR로 연결하는 것이 실습의 핵심입니다.

출처: [시험범위](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.pd7rhp5vffgr), [SQL Injection — gremlin](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.8dro0sijblpf)

## 17번. SQL 쿼리 수행 결과

**Docs 시험 힌트:** SQL 쿼리 수행 결과.

**Docs 수업 내용**

수업의 5행 예시입니다.

| 이름 | 비밀번호 |
| --- | --- |
| test | 1234 |
| choi | 4567 |
| kim | 1111 |
| park | 0000 |
| test | 9999 |

이 예시에서 이름이 choi이고 비밀번호가 1234인 조건은 일치하는 행이 없습니다. 이름이 choi이고 비밀번호가 4567인 조건은 한 행과 일치합니다.

16번의 AND·OR 조건과, 22번의 따옴표·주석 처리를 함께 확인합니다.

**원문 확인 필요:** 수업의 다른 8행 예시에는 AND 조건을 제시하면서 결과를 4행이라고 설명하는 부분이 있습니다. 제시된 조건과 결과 설명이 서로 맞지 않아 확정 결과로 외우거나 채점하지 않습니다.

출처: [SQL Injection](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.8dro0sijblpf)

## 18번. admin 문자열 필터 우회

**Docs 시험 힌트:** 웹서버가 'admin' 문자열을 필터링할 때 우회하는 방법.

**Docs 수업 내용**

goblin 수업에는 문자 코드와 16진수 표현을 사용하는 예시가 나옵니다.

~~~sql
char(97,100,109,105,110)
0x61646d696e
~~~

숫자 조건에서는 no=2를 이용하는 풀이도 다룹니다.

SQL Injection 마무리 수업에서는 Python의 문자열 포함 검사와 SQL 키워드의 대소문자 처리 차이를 활용하는 내용을 다룹니다.

**정답 적용 범위:** 필터와 쿼리 구조를 함께 봅니다. 문서에 나온 방식이 모든 DB·필터에서 통한다고 확대하지 않습니다.

출처: [SQL Injection — goblin](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.8dro0sijblpf), [SQL Injection 마무리](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ljvdeb9idd4h)

## 19번. MySQL 구조 정보 — information_schema

**Docs 시험 힌트:** MySQL에서 전체 데이터베이스 구성정보를 확인할 수 있는 특수한 스키마.

**Docs 수업 내용**

정답은 **information_schema**입니다. 수업에서 조회하는 구성정보입니다.

| 테이블 | 수업에서 확인하는 열 |
| --- | --- |
| information_schema.schemata | schema_name |
| information_schema.tables | table_schema, table_name |
| information_schema.columns | table_schema, table_name, column_name |

babyunion 실습에서는 UNION을 통해 스키마·테이블·열 이름을 확인한 뒤 숨겨진 테이블의 값을 찾습니다. @@version으로 버전을 확인하는 내용도 나옵니다.

출처: [SQL Injection 마무리 — babyunion](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ljvdeb9idd4h)

## 20번. 효과적인 SQL 공격 방식

**Docs 시험 힌트:** 효과적인 SQL 공격 방식.

**Docs 수업 내용**

수업에서는 **Blind SQL Injection**과 **UNION을 이용하는 방식**을 다룹니다.

| 방식 | 수업의 흐름 |
| --- | --- |
| Blind | 조건의 참·거짓을 보고 길이와 문자를 찾음 |
| UNION | 결과에 다른 조회 값을 합쳐 원하는 열을 화면에 표시 |

Blind 실습에 사용하는 표현입니다.

~~~sql
length(upw)
substr(upw,idx,1)
~~~

문자를 중간값과 비교하는 이진 탐색도 다룹니다. 대소문자 구분 문제에 대해서는 ASCII() 또는 binary를 이용하는 설명이 나옵니다.

UNION 수업에서는 babyunion의 4열 예시와 Flask의 idx·upw·uid 3열 예시를 각각 확인합니다. Flask 코드가 result[1]을 표시하기 때문에 두 번째 위치의 값을 맞추는 과정을 다룹니다.

**정답 적용 범위:** 열 수와 출력 위치는 각각의 수업 코드에 맞춰 확인합니다. 위 숫자를 모든 문제의 공통 조건으로 외우지 않습니다.

**원문 확인 필요:** binary+substr처럼 URL 표현과 SQL 표현이 섞인 부분은 환경과 실제 실행 형태를 확인해야 합니다. 독립적인 확정 구문으로 추가하지 않습니다.

출처: [SQL Injection 마무리](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ljvdeb9idd4h), [2학기 수행 기초2](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.r1pyvza0s9g5)

## 21번. Python Flask 웹서버 구성 유의사항

**Docs 시험 힌트:** Python Flask로 웹서버를 구성할 때 유의사항.

**Docs 수업 내용**

수업의 파일 배치입니다.

~~~text
app.py
flag.txt
templates/
    index.html
    login.html
static/
    css/
    js/
~~~

- pip install flask로 설치합니다.
- HTML 템플릿은 templates에 둡니다.
- CSS·JavaScript 파일은 static/css·static/js에 둡니다.
- 내려받은 파일 이름에 .js.다운로드가 붙었을 때 파일 이름을 정리합니다.
- flag.txt를 읽는 코드를 확인합니다.
- 정적 파일 수정이 반영되지 않는 상황과 캐시 응답 헤더를 다룹니다.

수업의 서버 실행 설정입니다.

~~~python
app.run(host='0.0.0.0', port=8000)
~~~

수업에서 로컬 접속 주소 127.0.0.1:8000을 확인하고, 다른 PC의 접속을 위해 인바운드 8000번 포트 설정을 진행합니다.

캐시 관련 코드입니다.

~~~python
@app.after_request
def set_response_headers(response):
    response.headers['Cache-Control'] = 'no-cache, no-store, must-revalidate'
    response.headers['Pragma'] = 'no-cache'
    response.headers['Expires'] = '0'
    return response
~~~

두 번째 수업에서는 DB 연결의 HOST·USER·PASSWORD·DB 설정, 실제 테이블 이름으로 쿼리 수정, DB 사용자 권한·방화벽 설정을 확인합니다. GET 입력에는 request.args를 사용합니다.

**원문 확인 필요:** 첫 수업의 “상대경로 지정 시 app.py가 기준위치”라는 문장은 일반적인 파일 열기의 기준으로 확정해 외우지 않습니다. 원문의 해당 설명은 별도 확인이 필요하며 퀴즈 정답에서 제외합니다.

출처: [2학기 수행 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ant3m5zchvie), [2학기 수행 기초2](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.r1pyvza0s9g5)

## 22번. SQL Injection 쿼리 구문 판별

**Docs 시험 힌트:** SQL 인젝션용 쿼리 구문 판별.

**Docs 수업 내용**

수업에서 확인할 순서입니다.

1. 입력이 들어가는 위치와 따옴표 종류를 확인합니다.
2. 기존 문자열을 닫는지 확인합니다.
3. AND·OR의 조건 결과를 확인합니다.
4. 입력 뒤에 남는 SQL을 주석으로 처리하는지 확인합니다.
5. 반환되는 행과 코드에서 검사하는 값을 확인합니다.

MySQL 수업의 주석 표현은 #, --, /* */입니다. -- 예시에는 뒤에 공백이 들어갑니다.

cobolt에서는 항상 참인 조건이 첫 행인 rubiya를 가져오는 상황을 확인하고, admin을 지정하는 다음 입력을 다룹니다.

~~~sql
admin' -- -
~~~

SQLite 기반 simpleSQLi에서는 쿼리가 큰따옴표로 입력을 감싸므로 다음 입력이 나옵니다.

~~~sql
admin" --
~~~

이 수업에서는 #을 사용했을 때의 실패와 --을 이용하는 과정을 비교합니다. LIMIT 1,1을 사용하는 풀이도 다룹니다.

**정답 적용 범위:** MySQL 예시와 SQLite 예시의 따옴표·주석을 섞어 공통 정답으로 만들지 않습니다.

출처: [SQL Injection — cobolt·simpleSQLi](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.8dro0sijblpf)

## 23번. SQL Injection 공백 우회

**Docs 시험 힌트:** SQL 인젝션의 공백 우회 기법.

**Docs 수업 내용**

SQL Injection 마무리 수업의 필터 목록입니다.

~~~python
['union', 'select', 'from', 'and', 'or', 'admin', ' ', '*', '/']
~~~

수업에서 다룬 사항입니다.

- /**/를 공백 대신 쓰는 방법을 검토하지만, 위 목록에서는 *와 /도 필터링됩니다.
- SQL 키워드의 대문자 표기를 활용합니다.
- 백틱으로 식별자를 감싸거나 괄호를 사용하는 구문을 다룹니다.
- URL 입력에서는 %09로 탭, %23으로 #을 표현하는 예시가 나옵니다.

**정답 적용 범위:** 공백을 바꾸는 방식과 키워드 필터를 피하는 방식은 구분해서 봅니다. 대문자 표기만으로 공백 문제가 해결된다고 외우지 않습니다.

> **이해 도움 — 추가 설명(시험 정답 아님):** 우회 후보를 고를 때는 바꾸려는 문자뿐 아니라 대체 표현에 들어가는 문자도 필터 목록과 비교하면 이해하기 쉽습니다.

출처: [SQL Injection 마무리](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.ljvdeb9idd4h)

## 24번. SSH로 Bandit 접속

**Docs 시험 힌트:** ssh로 Bandit 사이트 접속하기.

**Docs 수업 내용**

~~~bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
~~~

| 항목 | 수업 예시 |
| --- | --- |
| 계정 | bandit0 |
| 서버 | bandit.labs.overthewire.org |
| 접속 포트 | 2220 |
| 처음 접속하는 계정의 비밀번호 | bandit0 |

접속 종료 명령입니다.

~~~bash
exit
~~~

**정답 표현 기준:** 문서의 서버·계정·2220번 포트를 기준으로 합니다. 별도의 SSH 기본 포트 지식을 이 문제의 답에 추가하지 않습니다.

출처: [리눅스 기초](https://docs.google.com/document/d/1f-X2MPeM4wObP3Wqao8sELJo9UZCR-DpTJboYgqZ_Wo/edit?tab=t.6w305jslelsk)

---

## 원문 확인이 필요한 항목

- 3번 SSHD, 5번 ARP·Router, 6번 C&C 서버·로그 생성기·DDoS 탐지기: 시험범위에는 이름이 있지만 확인한 수업 텍스트에 정의가 없습니다.
- 7번: 질문의 정답 명칭이 직접 기재되어 있지 않습니다.
- 12번: 단계별 코드의 최종 변수와 일부 출력문의 변수명이 일치하지 않습니다.
- 17번: 8행 예시의 AND 조건과 결과 설명이 모순됩니다.
- 20번: URL 표기와 SQL 표현이 섞인 일부 binary 예시는 확정 구문으로 사용하지 않습니다.
- 21번: 상대경로 기준에 대한 원문 문장은 별도 확인이 필요합니다.

이 항목은 제가 추정해 정답을 채우지 않았습니다. 본문의 네 개 “이해 도움 — 추가 설명” 블록은 이해를 돕는 주석이며 암기 웹페이지의 정답 조건에 포함하지 않습니다.
