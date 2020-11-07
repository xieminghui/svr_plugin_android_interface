## 简介 Introduction
包含一些工具类，方便应用开发和使用 Skyworth VR 设备中特定的系统服务， 支持以下功能  
Contains some helper classes to facilitate application development and using of specific system services in Skyworth VR devices, which support the following functions
* ApkUtils
* AppUtils
* BatteryUtils
* BluetoothUtils
* BrightnessUtils
* DeviceUtils
* LocaleUtils
* PermissionUtils
* ProximitySensorUtils
* StorageUtils
* TimeUtils
* VolumeUtils
* WakeLockUtils
* WifiDisplayUtils
* WifiUtils

## 用法示例 Sample  
```java
public class MainActivity extends AppCompatActivity {
    AndroidInterface androidInterface;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        androidInterface = AndroidInterface.getInstance();
        androidInterface.init(getApplication());
        androidInterface.getWifiUtils().setListener2(new WifiUtils.WifiListener2() {

            @Override public void onOpened(boolean b) {

            }

            @Override public void onConnecting(int i, String s) {

            }

            @Override public void onSearchResult(ArrayList<WifiInfo> arrayList) {

            }

            @Override public void onRssiLevelChanegd(int i) {

            }
        });
    }

    @Override protected void onResume() {
        super.onResume();
        androidInterface.getWifiUtils().resume();
        androidInterface.getWifiUtils().searchWifi();
    }

    @Override protected void onPause() {
        super.onPause();
        androidInterface.getWifiUtils().pause();
    }

    @Override protected void onDestroy() {
        super.onDestroy();
        androidInterface.release();
    }
}
```

具体信息请阅读开发者文档  
Please read the developer documentation for details