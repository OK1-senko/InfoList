# AutoCAD カスタムUI実装手順書

## 1. 開発環境のセットアップ

### 必要なソフトウェア
- Visual Studio（2019以降推奨）
- AutoCAD（最新版推奨）
- .NET Framework 4.8以上

### AutoCAD開発用参照の準備
以下のDLLをプロジェクトに追加する必要があります：
- acdbmgd.dll
- acmgd.dll
- acwindows.dll

これらのDLLは通常、以下のパスにあります：
```
C:\Program Files\Autodesk\AutoCAD [バージョン]\
```

## 2. プロジェクトの作成

1. Visual Studioを起動
2. 「新しいプロジェクト」を選択
3. 「クラスライブラリ（.NET Framework）」を選択
4. プロジェクト名を入力（例：AutoCADCustomUI）
5. .NET Frameworkのバージョンを選択（AutoCADの対応バージョンに合わせる）

### 参照の追加手順
1. ソリューションエクスプローラーでプロジェクトを右クリック
2. 「参照の追加」を選択
3. 「参照」ボタンをクリック
4. 上記3つのDLLを選択して追加

## 3. コードの実装

### 基本構造の作成
1. 新しいクラスファイルを作成（例：CustomUICommand.vb）
2. 以下の名前空間を追加：
```vb
Imports Autodesk.AutoCAD.Runtime
Imports Autodesk.AutoCAD.ApplicationServices
Imports Autodesk.AutoCAD.Windows
```

### コマンドクラスの実装
1. CustomUICommandクラスを作成
2. ShowCustomUIメソッドを実装
3. カスタムフォームクラスを実装

## 4. ビルドと配置

### ビルド設定
1. プロジェクトのプロパティを開く
2. 「ビルド」タブで出力パスを設定
3. プラットフォームターゲットを「Any CPU」に設定
4. 「最適化」で「Prefer 32-bit」のチェックを外す

### ビルド手順
1. メニューから「ビルド」→「ソリューションのビルド」を選択
2. 生成されたDLLファイルを確認

## 5. AutoCADへの統合

### DLLの読み込み
1. AutoCADを起動
2. コマンドラインに「NETLOAD」と入力
3. 生成したDLLを選択して読み込む

### CUIへの登録
1. AutoCADで「CUI」コマンドを実行
2. 「カスタマイズ」タブを選択
3. 新しいタブまたはパネルを作成
4. コマンドリストに新しいコマンドを追加
   - コマンド名：SHOWCUSTOMUI
   - 説明：適切な説明を入力
   - マクロ：^C^CSHOWCUSTOMUI

## 6. 動作確認とテスト

### 基本的なテスト項目
1. コマンドの実行
2. UIの表示
3. 各機能の動作確認
4. AutoCADとの連携確認

### トラブルシューティング
- DLLが読み込めない場合
  - .NET Frameworkのバージョンを確認
  - DLLの依存関係を確認
- コマンドが認識されない場合
  - CUIの設定を確認
  - コマンド名の大文字小文字を確認

## 7. 保守とメンテナンス

### 更新手順
1. コードの修正
2. DLLの再ビルド
3. AutoCADの再起動
4. 新しいDLLの読み込み

### バックアップ
- ソースコードの管理
- ビルド済みDLLの保管
- CUI設定のエクスポート

## 注意事項

- AutoCADのバージョンアップ時は互換性を確認
- セキュリティ設定により、DLLの読み込みがブロックされる場合があります
- カスタムUIは、AutoCADのメインウィンドウに統合する形で実装することを推奨
