# Python 汎用テンプレート

このフォルダは、Python プロジェクトで汎用的に利用できるテンプレート構成をまとめたものです。  
GitHub を前提にしており、uv と venv の両方に対応しています。  
開発するプロジェクトの内容に合わせて、この構成をベースにファイルを配置してください。

## 想定環境

* 仮想環境管理：uv または venv
* GitHub でのバージョン管理を前提とした構成

## フォルダ構成例

以下は、一般的な Python プロジェクト構成の一例です。  
このテンプレートでは、`src` フォルダを中心にコードを整理する構成を想定しています。

```
python/general/
├─ README.md              # このファイル
├─ .gitignore             # 共通の除外設定（uv / venv 対応済み）
├─ .gitattributes         # 改行コード統一設定
├─ src/                   # メインの Python コードを配置
│   ├─ __init__.py
│   └─ main.py
├─ tests/                 # テストコード（unittest / pytestなど）
│   └─ test_main.py
├─ requirements.txt       # pip での依存関係管理に使用
├─ pyproject.toml         # uv / poetry / build 設定などを記述する場合に使用
└─ docs/                  # ドキュメント類を配置（任意）
```

## 仮想環境の作成方法

### uv を使用する場合

```bash
uv venv
uv pip install -r requirements.txt
```

### venv を使用する場合

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## プロジェクト作成の流れ

1. このフォルダの内容を新しいリポジトリまたはプロジェクトフォルダにコピーします。
2. 仮想環境（uv または venv）を作成します。
3. `.gitignore` により、仮想環境やキャッシュがコミット対象外になります。
4. `src/` にコードを追加し、`tests/` にテストコードを配置します。
5. 必要に応じて `pyproject.toml` を設定して依存管理やツール設定を統合します。

## 注意点

このテンプレートは汎用構成を示しているため、プロジェクトの種類（CLIツール、Webアプリ、API など）に応じてディレクトリや設定ファイルを追加してください。  
`.gitignore` と `.gitattributes` は既にこのテンプレート内に含まれており、そのまま利用できます。
