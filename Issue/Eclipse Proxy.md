<h3>이클립스 외부 연동 불가 현상</h3>

\# Market Place 접속 오류<br/><br/>
![image](https://user-images.githubusercontent.com/44637739/93281539-42f47d00-f807-11ea-8cc7-e9d49d8abf48.png)

\# New Install 접속오류<br/><br/>

<이미지 없음><br/><br/>

<h3> 해결 </h3>

1. 인증서 다운로드 및 루트 기관에 저장
- 인증서 다운로드 ( escort > utility > 소프트웨어 > 프록시 인증서파일(수동설치) 다운로드 )
- 인증서 설치 선택 -> 인증서 가져오기 마법사 시작 (다음 선택) ->  모든 인증서를 다음 장소에 저장 -> 찾아보기<br/>
   -> 신뢰할 수 있는 루트 인증기관에 저장

2. 자바에 인증서 매핑
- keytool -storepass changeit -import -file "C:\Program Files\Java\jre1.8.0_181\lib\security\Samsung(0).crt" -keystore "C:\Program Files\Java\jre1.8.0_181\lib\security\cacerts" -alias samsungcert1
- "C:\Program Files\Java\jre1.8.0_181\bin\keytool.exe" -import -file "C:\Program Files\Java\jre1.8.0_181\lib\security\Samsung(0).crt" -keystore "C:\Program Files\Java\jre1.8.0_181\lib\security\cacerts"  

3. 프록시 설정
- Eclipse Windows - Preferences > General - Network Connections - Active Provider를 Manual로 변경.
- HTTP 및 HTTPS 변경 ( Proxy IP:Port ) - 수원 사업장 Proxy
 => 수동프록시이므로, DNS 로 구성된 자동프록시 : 8088 시도해볼것
