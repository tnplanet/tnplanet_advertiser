# TheNewPlanet Android SDK 연동 가이드

- 본 SDK 를 통해 액션형과 실행형 광고를 진행할 수 있다.
- 안드로이드 버전 요구사항 : 2.2(API Level 8) 이상

## 1. 프로젝트에 SDK 추가
- SDK 다운로드 후 압축을 해제합니다.
- tnplanet_advertiser.jar 파일을 프로젝트(예를 들면 libs 폴더 안)에 추가합니다.

## 2. AndroidManifest.xml 파일 수정
- AndroidManifest.xml 파일 내에 아래와 같이 권한을 추가합니다.
- 해당 권한이 이미 있는경우 다음 단계로 넘어갑니다.

```Xml
<manifest>
    ...
    <!-- Permission for BuzzAd-->
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.READ_PHONE_STATE" />
</manifest>
