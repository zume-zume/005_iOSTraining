# ReadMe

## 諸々基本的なこと
### 変数と定数
**変数の宣言**
```
ver 変数名: 型名
```
**定数の宣言**
```
let 定数名: 型名
```
  
### objectiveCとの連携
こんな感じで書く  
  
**ObjcClass.h**  
```
#import <Foundation/Foundation.h>
@interface ObjcCalss : NSObject
@property(nonatomic, strong) SNString *name;
- (void)printName;
@end
```

**ObjcClass.m**
```
#import <ObjcClass.h>
@inplementation ObjcClass

- (void)printName {
    NSLog(@"My Name is %@", _name);
}
@end
```

**Bridging-Header.h**
```
#import "ObjcClass.h"
```

**main.swift**
```
let objcClass = ObjcClass()
objcClass.name = "Yamada Hanatarou"
objcClass.printName()
```

## 初期設定的なこと
### .mdファイルの識別
.mdファイルにmarkdownを適用するには、xcodeproj配下に、  
xcodesamplecode.plistというファイルを作っておかなければならないらしい。  
ファイルを置いてさえすればよくて、空でもいいらしい。  
  
### コミット&プッシュ
ツールバー > Source Control > Commit  
から、コミットしたい任意のファイルを選択して、コミットメッセージを入力してCommit  
  
その後、Pushする。（リモート上の変更が取り込まれていないよ〜のメッセージが出たら、Pullしてあげる）
