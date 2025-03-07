# 行政文書情報管理と提供 API仕様

## 1. 文書一覧取得

- **URL**: `/api/documents`
- **Method**: GET
- **Description**: 行政文書の一覧を取得します。
- **Parameters**:
  - `search`: 検索条件（オプション）
  - `page`: ページ番号（オプション）
  - `limit`: 1ページあたりの文書数（オプション）
  - `year`: 作成年度でのフィルタリング（オプション）
  - `department`: 文書保有課でのフィルタリング（オプション）
  - `document_number`: 文書管理番号でのフィルタリング（オプション）
- **Response**:
  - `documents`: 文書の配列
    - `year`: 作成年度
    - `department`: 文書保有課
    - `document_number`: 文書管理番号
    - `title`: 文書件名
    - `created_date`: 作成日
    - `storage_period`: 保存期間
  - `total`: 文書の総数

## 2. 文書詳細取得

- **URL**: `/api/documents/{id}`
- **Method**: GET
- **Description**: 指定されたIDの文書詳細を取得します。
- **Parameters**:
  - `id`: 文書のID
- **Response**:
  - `document`: 文書の詳細情報
    - `year`: 作成年度
    - `department`: 文書保有課
    - `document_number`: 文書管理番号
    - `title`: 文書件名
    - `created_date`: 作成日
    - `storage_period`: 保存期間
    - その他詳細情報



# documents テーブル構成

## テーブルカラム

- **id**: 主キー
- **title**: 文書件名
- **created_at**: 文書作成日
- **document_number**: 文書番号 (VARCHAR)
- **document_department**: 文書保有課 (VARCHAR)
- **storage_period**: 保存期間
- **content**: 文書内容
- **completion_date**: 完了年月日 (DATE)