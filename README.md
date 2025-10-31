# TaiSEIA_ESPhome_samples

感謝[洋蔥大神](https://github.com/tsunglung/taixia)開發TaiSEIA for ESPhome，才能有此範例

此範例使用[MH-ET LIVE minikit for ESP32](https://doc.riot-os.org/group__boards__esp32__mh-et-live-minikit.html)硬體，新版本改用[ESP32C3](https://www.nologo.tech/product/esp32/esp32c3/esp32c3supermini/esp32C3SuperMini.html)體積更小，另加DC-DC轉5V(國際牌)與level shifter轉3.3V

適用廠牌: **國際牌壁掛冷氣、日立壁掛&吊隱冷氣、日立除濕機**

適用型號: 可外接原廠Wi-Fi智慧模組的機型，安裝簡單方便

根據廠牌與機器分開範例，基本上只要修改最頂端的兩個名稱即可，方便OTA與辨識是哪一台

請根據下表選擇適合的檔案燒錄

| 檔名 | 適用廠牌 | 燒錄方式 | 適用模組(外觀) | Bin檔 | YAML |
|-------|:-----:|:-----:|:-----:|:-----:|-------|
| c3-mini-climate-h.factory.bin | 日立冷氣 |  接USB直接燒錄  | ESP32C3(小) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/c3-mini-climate-h.factory.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Hitachi/Climate-ESP32C3.yaml) |
| c3-mini-climate-h.ota.bin | 日立冷氣 |  web server OTA用  | ESP32C3(小) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/c3-mini-climate-h.ota.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Hitachi/Climate-ESP32C3.yaml) |
| c3-mini-climate-p.factory.bin | 國際牌冷氣 |  接USB直接燒錄  | ESP32C3(小) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/c3-mini-climate-p.factory.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Panasonic/Climate-sample-ESP32C3.yaml) |
| c3-mini-climate-p.ota.bin |  國際牌冷氣  |  web server OTA用  | ESP32C3(小) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/c3-mini-climate-p.ota.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Panasonic/Climate-sample-ESP32C3.yaml) |
| c3-mini-dehumidifier.factory.bin |  日立除濕機  |  接USB直接燒錄  | ESP32C3(小) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/c3-mini-dehumidifier.factory.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Hitachi/Dehumidifier-ESP32C3.yaml) |
| climate-h.factory.bin |  日立冷氣  |  接USB直接燒錄  | ESP32(大) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/climate-h.factory.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Hitachi/Climate-ESP32.yaml) |
| climate-h.ota.bin |  日立冷氣  |  OTA專用  | ESP32(大) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/climate-h.ota.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Hitachi/Climate-ESP32.yaml) |
| climate-p.factory.bin |  國際牌冷氣  |  接USB直接燒錄  | ESP32(大) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/climate-p.factory.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Panasonic/Climate-sample-ESP32.yaml) |
| climate-p.ota.bin |  國際牌冷氣  |  web server OTA用  | ESP32(大) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/climate-p.ota.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Panasonic/Climate-sample-ESP32.yaml) |
| dehumidifier.factory.bin |  日立除濕機  |  接USB直接燒錄  | ESP32(大) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/dehumidifier.factory.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Hitachi/Dehumidifier-ESP32.yaml) |
| dehumidifier.ota.bin |  日立除濕機  |  OTA專用  | ESP32(大) | [Bin檔](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/dehumidifier.ota.bin) | [YAML](https://github.com/xangin/TaiSEIA_ESPhome_samples/blob/main/Hitachi/Dehumidifier-ESP32.yaml) |

## 如何下載

點擊檔案名稱>點右上角有個下載的圖案(Download Raw file)>儲存

## 使用方法

### A. 透過USB

1. 下載名稱結尾是factory.bin的檔案
2. 模組透過usb接上電腦
3. 用chrome或edge瀏覽器前往 [https://web.esphome.io](https://web.esphome.io/)
4. 按Connect>選擇寫有USB Single Serial(大)或USB JTAG(小)>按INSTALL>選擇剛儲存的Bin檔，等待燒錄完成
5. 顯示finish後，就可看到ESP32上面的藍燈開始閃爍，這時候等待久一點，會看到有熱點跑出來
6. 點連線並輸入Wi-Fi密碼: 12345678
7. 連上後輸入http://192.168.4.1
8. 進到網頁選擇家中Wi-Fi名稱及輸入密碼後按儲存，連上後HA應該就會自動發現此裝置

### B. OTA

1. 下載名稱結尾是ota.bin的檔案
2. 在瀏覽器網址列輸入裝置IP
3. 最下方OTA Update選擇ota.bin檔>按Update，等待畫面跳轉為done即完成

