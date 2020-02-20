# 交互秘術
使用標準node.js交互。

## 安裝
```
wyg i 交互秘術
```
或
```
wyg i jiaohu
```

## 使用
```
吾嘗觀「「交互秘術」」之書。方悟
「正閱」
「已閱」
「化言」
「發生」
「監聽」
「閱止」
「輸出」
之義。
```

| Wenyan | Node.js |
| ------ | ------ |
| `寫「甲」焉` | `process.stdout.write(甲);` |
| `施「化言」於「甲」` | `甲 = 甲.toString();` |
| `「正閱」` | `"data"` |
| `「已閱」` | `"end"` |
| `施「閱止」` | `process.stdin.end();` |
| `生「甲」之事` | `process.stdin.emit(甲);` |
| `聽得「甲」之事乃行「乙」之術` | `process.stdin.on(甲, 乙);` |

## 注意事項
輸入所得為`Buffer`，須施`「化言」`於之，以化之為`言`。  

輸入完成後按`Enter`結束輸入，`Enter`將輸入一個換行符（`\n`或`\r\n`）。回調函數`「乙」`處理時，應注意這個換行符，不能忽略。  

使用`書之`輸出時，會在結尾自動添加一個換行符；若使用`寫「甲」焉`輸出，則不會添加換行符。

欲行`聽得「甲」之事乃行「乙」之術`，須先悟`「監聽」`之義；  
欲行`生「甲」之事`，須先悟`「發生」`之義；  
欲行`寫「甲」焉`，須先悟`「輸出」`之義；  

可用`但聞「甲」之事乃行「乙」之術`代替`聽得「甲」之事乃行「乙」之術`，其義蓋同。([#1](https://github.com/GLanguage/jiaohu-wy/issues/1))

## 一例

```
吾嘗觀「「交互秘術」」之書。方悟
「正閱」
「已閱」
「化言」
「發生」
「監聽」
「閱止」
「輸出」
之義。

吾有一術。名之曰「響應」。欲行是術。必先得一言。曰「輸入」。乃行是術曰。
    施「化言」於「輸入」。昔之「輸入」者今其是矣。
    寫「輸入」焉。
    生「已閱」之事。
是謂「響應」之術也。

聽得「正閱」之事乃行「響應」之術。
聽得「已閱」之事乃行「閱止」之術。
```
輸入：
```
問天地好在！

```
輸出：
```
問天地好在！

```
注意：輸入中包含了一個換行符，輸出中也有一個換行符。
