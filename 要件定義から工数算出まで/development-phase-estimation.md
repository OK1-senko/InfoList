# 開発フェーズ別 工数見積もりガイド

## 1. 要件定義・分析期間

### 見積もり項目
- 現状業務分析
- 要件ヒアリング
- 要件整理・分析
- 要件定義書作成
- レビュー・承認

### 工数算出方法
1. 基本工数 = （ヒアリング対象部署数 × 2人日）＋（主要機能数 × 1人日）
2. 要件定義書作成 = （主要機能数 × 0.5人日）
3. レビュー・修正 = 基本工数の20%

### 考慮すべき要素
- ステークホルダーの数と所在地
- 業務の複雑性
- 既存システムの有無
- 類似案件の経験

## 2. 基本設計期間

### 見積もり項目
- システム方式設計
- 機能設計
- 画面・帳票設計
- データベース設計
- 外部インターフェース設計

### 工数算出方法
1. システム方式設計 = 3〜5人日
2. 機能設計 = （画面数 × 1人日）＋（バッチ処数 × 1人日）
3. データベース設計 = （テーブル数 × 0.5人日）
4. 外部IF設計 = （IF数 × 1人日）

### 考慮すべき要素
- システムの規模
- 技術的な複雑さ
- セキュリティ要件
- パフォーマンス要件

## 3. 詳細設計期間

### 見積もり項目
- 詳細機能設計
- プログラム設計
- データベース詳細設計
- 入出力設計
- エラー処理設計

### 工数算出方法
1. 詳細機能設計 = （画面数 × 2人日）＋（バッチ処理数 × 2人日）
2. DB詳細設計 = （テーブル数 × 1人日）
3. エラー処理設計 = 基本機能数 × 0.5人日

### 考慮すべき要素
- プログラムの複雑度
- 再利用可能なコンポーネントの有無
- チーム体制

## 4. 実装期間

### 見積もり項目
- 画面実装
- ロジック実装
- データベース実装
- 単体テスト実装

### 工数算出方法
1. 画面実装 = （画面数 × CRUD複雑度係数）
   - 単純なCRUD: 3人日
   - 中程度の複雑さ: 5人日
   - 複雑な処理を含む: 8人日
2. ロジック実装 = （機能数 × 複雑度係数）
3. DB実装 = テーブル数 × 0.5人日

### 考慮すべき要素
- 開発言語・フレームワークの習熟度
- コーディング規約の厳密さ
- レビュー体制

## 5. テスト期間

### 見積もり項目
- 単体テスト
- 結合テスト
- システムテスト
- 受入テスト

### 工数算出方法
1. 単体テスト = 実装工数の40%
2. 結合テスト = 実装工数の30%
3. システムテスト = 実装工数の40%
4. 受入テスト支援 = 実装工数の20%

### 考慮すべき要素
- テスト自動化の程度
- 品質要件の厳密さ
- テストデータの量

## 6. リリース準備期間

### 見積もり項目
- 環境構築
- デプロイ手順作成
- 運用手順作成
- 教育・トレーニング
- 本番移行計画作成

### 工数算出方法
1. 環境構築 = システム規模により3-10人日
2. 手順書作成 = （主要機能数 × 0.5人日）
3. トレーニング = （対象者数 ÷ 10）× 2人日

### 考慮すべき要素
- システム環境の複雑さ
- 運用体制
- エンドユーザーの規模

## 一般的な補正要素

1. チーム経験係数
   - 経験豊富: 0.8
   - 標準的: 1.0
   - 経験少: 1.3

2. プロジェクト規模係数
   - 小規模（3ヶ月未満）: 1.0
   - 中規模（3-6ヶ月）: 1.1
   - 大規模（6ヶ月以上）: 1.2

3. 技術的難易度係数
   - 低: 0.9
   - 中: 1.0
   - 高: 1.3

4. ビジネス複雑度係数
   - 低: 0.9
   - 中: 1.0
   - 高: 1.2
