# ReadMe

## 諸々基本的なこと
### 変数と定数
ver 変数の宣言  
let 定数の宣言   
  
### objectiveCとの連携
**ObjcClass.h**  
```
#import <Foundation/Foundation.h>
@interface ObjcCalss : NSObject
@property(nonatomic, strong) SNString *name;
- (void)printName;
@end
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
