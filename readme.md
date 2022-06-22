# ReadMe

##swiftUI
  
###プレビューの表示
Editor > CanvasでCanvas（プレビュー）を表示させることができる。
※右上の三みたいなところからも起動できる。  
  
###Swift Inspector
コード又はプレビューの任意の場所でCmd + click  
プレビュから動的に文字のフォントや色を設定することができる。

###H・V・ZStack
- HStack:水平方向に子Viewを配置
- VStack:垂直方向に子Viewを配置
- ZStack:親Viewと子Viewを重ねることができる
  
###spacer（スパーサー）
子Viewが、親Viewが持つスペースの全てを利用するように拡張する。

###Assets（アセット）
画像はAssets.xcassetsで管理。ここに載っけている名前をswiftファイルで指定することで、  
swiftファイルから画像を読み込むことができる。  
.clipShape(Circle())で丸くしたり、四角で表示したり影つけたり色々できる。  
  
1x,2x,3xとあるが、1xは1倍の画像。例えば1xはiphone3。2xはiPhone8。3xはiPhoneX。  
と言ったように、機種ごとに画素が異なるので、対応する画像が決まっている。  
ちゃんとやるのであれば、3パターンの画像を用意してあげる必要がある。  
  
けど、それは面倒なので、PDFのベクター画像を作ってあげれば解決するらしい。  
[vectorization](https://www.vectorization.org/)でPDFで吐き出してあげて、  
1xにだけ設定して、scaleをsingle Scaleにしてあげるといい。  

※余談：ベクター画像は解像度に依存しない（拡大縮小してもボケない）画像  
ラスター画像は解像度に依存する（拡大縮小するとボケちゃう）画像のこと  
  
## swiftの基本的なこと
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
  
### 関数の呼び出し
**呼び出す式**
```
関数名(引数名1: 引数1, 引数名2: 引数2...)
```
  
### Xcodeでのコミット&プッシュ
ツールバー > Source Control > Commit  
から、コミットしたい任意のファイルを選択して、コミットメッセージを入力してCommit  
  
その後、Pushする。（リモート上の変更が取り込まれていないよ〜のメッセージが出たら、Pullしてあげる）
  
## 初期設定的なこと
### .mdファイルの識別
.mdファイルにmarkdownを適用するには、xcodeproj配下に、  
xcodesamplecode.plistというファイルを作っておかなければならないらしい。  
ファイルを置いてさえすればよくて、空でもいいらしい。  
