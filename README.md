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
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.READ_PHONE_STATE" />
</manifest>
```

## 3. 함수 추가
- TheNewPlanet.Init(Context context, String App_key) : CPI 상품일 경우 호출 합니다.
- TheNewPlanet.Excute(Context context, String App_key) :  CPE 상품일 경우 호출 합니다.

##### 실행형
실행후 처음 호출되는 액티비티 생성 시점에 호출합니다.
```Java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    // App_key : 담당자에게 발급받은 키값
    TheNewPlanet.Init(this, "App_key");
}
```

##### 액션형
액션완료 시점에 호출합니다.

```Java
void onAction() {
    // App_key : 담당자에게 발급받은 키값
    TheNewPlanet.Excute(this, "App_key");
}
```

## 4. 테스트 완료 후 광고 집행
위 과정을 통해 연동한 apk 파일을 담당자에게 메일을 주시면 테스트 후에 광고가 진행됩니다.
