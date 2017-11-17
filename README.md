# iphone-model-identifier-list
通过utsname获取iphone设备identifier所对应的设备列表

### 核心代码
```swift
extension UIDevice {
  
  var modelName: String {
    
    var systemInfo = utsname()
    uname(&systemInfo)
    
    let machine = systemInfo.machine
    let mirror = Mirror(reflecting: machine)
    var identifier = ""
    
    for child in mirror.children where child.value as? Int8 != 0 {
      identifier.append(String(UnicodeScalar(UInt8(child.value as! Int8))))
    }
    
    return identifier
  }
  
}
```

### 使用方法
```swift
let deviceName = UIDevice.current.modelName
```

### iPhone列表
|   机型  |device_name|
|--------|:--------:|
| iPhone (Original/1st Gen/EDGE) | iPhone1,1 |
| iPhone 3G | iPhone1,2 |
| iPhone 3G (China/No Wi-Fi) | iPhone1,2* |
| iPhone 3GS | iPhone2,1 |
| iPhone 3GS (China/No Wi-Fi) | iPhone2,1* |
| iPhone 4 (GSM) | iPhone3,1 |
| iPhone 4 (GSM, Revision A) | iPhone3,2 |
| iPhone 4 (CDMA/Verizon/Sprint) | iPhone3,3 |
| iPhone 4S (4s*) | iPhone4,1 |
| iPhone 4S (GSM China/WAPI) | iPhone4,1* |
| iPhone 5 (GSM/LTE 4, 17/North America) | iPhone5,1 |
| iPhone 5 (GSM/LTE 1, 3, 5/International) | iPhone5,1 |
| iPhone 5 (GSM/LTE/AWS/North America) | iPhone5,1 |
| iPhone 5 (CDMA/LTE, Sprint/Verizon/KDDI) |iPhone5,2 |
| iPhone 5 (CDMA China/UIM/WAPI) | iPhone5,2 |
| iPhone 5c (GSM/North America/A1532) | iPhone5,3 |
| iPhone 5c (CDMA/Verizon/A1532) | iPhone5,3 |
| iPhone 5c (CDMA/China Telecom/A1532) | iPhone5,3 |
| iPhone 5c (CDMA/US/Japan/A1456) | iPhone5,3 |
| iPhone 5c (UK/Europe/Middle East/A1507) |iPhone5,4 |
| iPhone 5c (China Unicom/A1526) |iPhone5,4 |
| iPhone 5c (Asia Pacific/A1529) |iPhone5,4 |
| iPhone 5c (China Mobile/A1516) |iPhone5,4 |
| iPhone 5s (GSM/North America/A1533) | iPhone6,1 |
| iPhone 5s (CDMA/Verizon/A1533) | iPhone6,1 |
| iPhone 5s (CDMA/China Telecom/A1533) | iPhone6,1 |
| iPhone 5s (CDMA/US/Japan/A1453) | iPhone6,1 |
| iPhone 5s (UK/Europe/Middle East/A1457) | iPhone6,2 |
| iPhone 5s (China Unicom/A1528) | iPhone6,2 |
| iPhone 5s (Asia Pacific/A1530) | iPhone6,2 |
| iPhone 5s (China Mobile/A1518) | iPhone6,2 |
| iPhone 6 Plus (GSM/North America/A1522) | iPhone7,1 |
| iPhone 6 Plus (CDMA/Verizon/A1522) | iPhone7,1 |
| iPhone 6 Plus (Global/Sprint/A1524) | iPhone7,1 |
| iPhone 6 Plus (China Mobile/A1593) | iPhone7,1 |
| iPhone 6 (GSM/North America/A1549) | iPhone7,2 |
| iPhone 6 (CDMA/Verizon/A1549) | iPhone7,2 |
| iPhone 6 (Global/Sprint/A1586) | iPhone7,2 |
| iPhone 6 (China Mobile/A1589) | iPhone7,2 |
| iPhone 6s (AT&T/SIM Free/A1633) | iPhone8,1 |
| iPhone 6s (Global/A1688) | iPhone8,1 |
| iPhone 6s (Mainland China/A1700) | iPhone8,1 |
| iPhone 6s (China Mobile/A1691) | iPhone8,1 |
| iPhone 6s Plus (AT&T/SIM Free/A1634) | iPhone8,2 |
| iPhone 6s Plus (Global/A1687) | iPhone8,2 |
| iPhone 6s Plus (Mainland China/A1699) | iPhone8,2 |
| iPhone 6s Plus (China Mobile/A1690) | iPhone8,2 |
| iPhone SE (United States/A1662) | iPhone8,4 |
| iPhone SE (Global/Sprint/A1723) | iPhone8,4 |
| iPhone SE (China Mobile/A1724) | iPhone8,4 |
| iPhone 7 (Verizon/Sprint/China/A1660) | iPhone9,1 |
| iPhone 7 (Japan/A1779) | iPhone9,1 |
| iPhone 7 (China Mobile/A1780) | iPhone9,1 |
| iPhone 7 Plus (Verizon/Sprint/China/A1661) | iPhone9,2 |
| iPhone 7 Plus (Japan/A1785) | iPhone9,2 |
| iPhone 7 Plus (China Mobile/A1786) | iPhone9,2 |
| iPhone 7 (AT&T/T-Mobile/Global/A1778) | iPhone9,3 |
| iPhone 7 Plus (AT&T/T-Mobile/Global/A1784) | iPhone9,4 |
| iPhone 8 (Verizon/Sprint/China/A1863) | iPhone10,1 |
| iPhone 8 (Japan/A1906) | iPhone10,1 |
| iPhone 8 Plus (Verizon/Sprint/China/A1864) | iPhone10,2 |
| iPhone 8 Plus (Japan/A1898) | iPhone10,2 |
| iPhone X (Verizon/Sprint/China/A1865) | iPhone10,3 |
| iPhone X (Japan/A1902) | iPhone10,3 |
| iPhone 8 (AT&T/T-Mobile/Global/A1905) | iPhone10,4 |
| iPhone 8 Plus (AT&T/T-Mobile/Global/A1897) | iPhone10,5 |
| iPhone X (AT&T/T-Mobile/Global/A1901) | iPhone10,4 |

### iPad列表
|   机型  |device_name| 
|--------|:--------:|
| iPad Wi-Fi (Original/1st Gen) | iPad1,1  |
| iPad Wi-Fi/3G/GPS (Original/1st Gen) | iPad1,1 |
| iPad 2 (Wi-Fi Only) | iPad2,1  |
| iPad 2 (Wi-Fi/GSM/GPS) | iPad2,2  |
| iPad 2 (Wi-Fi/CDMA/GPS) | iPad2,3  |
| iPad 2 (Wi-Fi Only, iPad2,4) | iPad2,4  |
| iPad mini (Wi-Fi Only/1st Gen) | iPad2,5  |
| iPad mini (Wi-Fi/AT&T/GPS - 1st Gen) | iPad2,6  |
| iPad mini (Wi-Fi/VZ & Sprint/GPS - 1st Gen) | iPad2,7  |
| iPad 3rd Gen (Wi-Fi Only) | iPad3,1  |
| iPad 3rd Gen (Wi-Fi/Cellular Verizon/GPS) | iPad3,2  |
| iPad 3rd Gen (Wi-Fi/Cellular AT&T/GPS) | iPad3,3  |
| iPad 4th Gen (Wi-Fi Only) | iPad3,4  |
| iPad 4th Gen (Wi-Fi/AT&T/GPS) | iPad3,5  |
| iPad 4th Gen (Wi-Fi/Verizon & Sprint/GPS) | iPad3,6  |
| iPad Air (Wi-Fi Only) | iPad4,1 |
| iPad Air (Wi-Fi/Cellular) | iPad4,2 |
| iPad Air (Wi-Fi/TD-LTE - China) | iPad4,3 |
| iPad mini 2 (Retina/2nd Gen, Wi-Fi Only) | iPad4,4|
| iPad mini 2 (Retina/2nd Gen, Wi-Fi/Cellular) | iPad4,5 |
| iPad mini 2 (Retina/2nd Gen, China) | iPad4,6 |
| iPad mini 3 (Wi-Fi Only) | iPad4,7 |
| iPad mini 3 (Wi-Fi/Cellular) | iPad4,8 |
| iPad mini 3 (Wi-Fi/Cellular, China) | iPad4,9 |
| iPad mini 4 (Wi-Fi Only) | iPad5,1 |
| iPad mini 4 (Wi-Fi/Cellular) | iPad5,2 |
| iPad Air 2 (Wi-Fi Only) | iPad5,3 |
| iPad Air 2 (Wi-Fi/Cellular) | iPad5,4 |
| iPad Pro 9.7-Inch (Wi-Fi Only) | iPad6,3 |
| iPad Pro 9.7-Inch (Wi-Fi/Cellular) | iPad6,4 |
| iPad Pro 12.9-Inch (Wi-Fi Only) | iPad6,7 |
| iPad Pro 12.9-Inch (Wi-Fi/Cellular) | iPad6,8 |
| iPad 9.7-Inch 5th Gen (Wi-Fi Only) | iPad6,11 |
| iPad 9.7-Inch 5th Gen (Wi-Fi/Cellular) | iPad6,12 |
| iPad Pro 12.9-Inch (Wi-Fi Only - 2nd Gen) | iPad7,1 |
| iPad Pro 12.9-Inch (Wi-Fi/Cell - 2nd Gen) | iPad7,2 |
| iPad Pro 10.5-Inch (Wi-Fi Only) | iPad7,3 |
| iPad Pro 10.5-Inch (Wi-Fi/Cellular) | iPad7,4 |

### iPod列表
|   机型  |device_name| 
|--------|:--------:|
| iPod touch (Original/1st Gen)  | iPod1,1 |
| iPod touch (2nd Gen) | iPod2,1 |
| iPod touch (2nd Gen/2009/8 GB) | iPod2,1 |
| iPod touch (3rd Gen/32 & 64 GB) | iPod3,1 |
| iPod touch (4th Gen/FaceTime) | iPod4,1 |
| iPod touch (4th Gen, 2011) | iPod4,1 |
| iPod touch (4th Gen, 2012) | iPod4,1 |
| iPod touch (5th Gen) | iPod5,1 |
| iPod touch (5th Gen, No iSight, 2013) | iPod5,1 |
| iPod touch (5th Gen, 16 GB, 2014) | iPod5,1 |
| iPod touch (6th Gen, 2015) | iPod7,1 |



<!-- 设备列表参考来自http://www.everyi.com/by-identifier/ipod-iphone-ipad-specs-by-model-identifier.html -->

