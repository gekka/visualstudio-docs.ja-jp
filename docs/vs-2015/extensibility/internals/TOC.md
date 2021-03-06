# [Visual Studio SDK の内部](inside-the-visual-studio-sdk.md)
# [Visual Studio シェル](visual-studio-shell.md)
# [ユーザー設定のサポート](support-for-user-settings.md)
# [Microsoft ヘルプ ビューアー SDK](microsoft-help-viewer-sdk.md)
# [コマンド、メニュー、およびツール バー](commands-menus-and-toolbars.md)
## [VSPackage でユーザー インターフェイス要素を追加する方法](how-vspackages-add-user-interface-elements.md)
## [Visual Studio Command Table (.Vsct) ファイル](visual-studio-command-table-dot-vsct-files.md)
### [.Vsct ファイルの編集](authoring-dot-vsct-files.md)
### [XML コマンド テーブル (.Vsct) ファイルの設計](designing-xml-command-table-dot-vsct-files.md)
### [方法: .Vsct ファイルを作成する](how-to-create-a-dot-vsct-file.md)
### [VSCT コンパイラのコマンドライン フラグ](vsct-compiler-command-line-flags.md)
## [既定のコマンド、グループ、およびツール バーの配置](default-command-group-and-toolbar-placement.md)
## [IDE 定義コマンド、メニュー、およびグループ](ide-defined-commands-menus-and-groups.md)
### [Visual Studio メニューの GUID および ID](guids-and-ids-of-visual-studio-menus.md)
### [Visual Studio ツール バーの GUID および ID](guids-and-ids-of-visual-studio-toolbars.md)
### [Visual Studio コマンドの GUID および ID](guids-and-ids-of-visual-studio-commands.md)
## [コマンド デザイン](command-design.md)
### [実装](command-implementation.md)
### [利用可能性](command-availability.md)
### [ルーティング アルゴリズム](command-routing-algorithm.md)
### [配置のガイドライン](command-placement-guidelines.md)
## [メニュー、ツール バー コマンドの最適化](optimizing-menu-and-toolbar-commands.md)
## [コマンドを使用可能にする](making-commands-available.md)
## [相互運用機能アセンブリを使用するコマンドとメニュー](commands-and-menus-that-use-interop-assemblies.md)
### [相互運用機能アセンブリを使用したコマンドのステータスの特定](determining-command-status-by-using-interop-assemblies.md)
### [相互運用機能アセンブリでのコマンドのコントラクト](command-contracts-in-interop-assemblies.md)
### [相互運用機能アセンブリ コマンド ハンドラーの登録](registering-interop-assembly-command-handlers.md)
### [Visual Studio 相互運用機能アセンブリの使用](using-visual-studio-interop-assemblies.md)
## [Vspackage のコマンド ルーティング](command-routing-in-vspackages.md)
# [VSPackage](vspackages.md)
## [VSPackage ファイルの場所を VS Shell に指定する](specifying-vspackage-file-location-to-the-vs-shell.md)
## [VSPackage のリソース](resources-in-vspackages.md)
## [VSPackage のセキュリティのベスト プラクティス](best-practices-for-security-in-vspackages.md)
## [VSPackage の登録](registering-vspackages.md)
# [ドキュメント ウィンドウ](document-windows.md)
## [ドキュメント テーブルの実行](running-document-table.md)
### [RDT_ReadLock の使用法](rdt-readlock-usage.md)
### [ドキュメント テーブルの保存と実行](persistence-and-the-running-document-table.md)
## [ドキュメントの読み込みの遅延](delayed-document-loading.md)
# [従来の言語サービスの機能拡張](legacy-language-service-extensibility.md)
## [従来の言語サービスの移行](migrating-a-legacy-language-service.md)
## [従来の言語サービスの基本情報](legacy-language-service-essentials.md)
## [従来の言語サービスの開発](developing-a-legacy-language-service.md)
### [従来の言語サービスのモデル](model-of-a-legacy-language-service.md)
### [従来の言語サービスのインターフェイス](legacy-language-service-interfaces.md)
### [従来の言語サービスのコマンドの受信](intercepting-legacy-language-service-commands.md)
#### [言語サービス フィルターの重要なコマンド](important-commands-for-language-service-filters.md)
### [従来の言語サービスの登録](registering-a-legacy-language-service2.md)
### [チェック リスト: 従来の言語サービスの作成](checklist-creating-a-legacy-language-service.md)
### [従来の言語サービスの特徴](legacy-language-service-features2.md)
#### [従来の言語サービスでの構文の色分け表示](syntax-coloring-in-a-legacy-language-service.md)
##### [構文の色分け表示の実装](implementing-syntax-coloring.md)
##### [方法: ビルトインの配色可能な項目の使用](how-to-use-built-in-colorable-items.md)
##### [カスタムの配色可能な項目](custom-colorable-items.md)
#### [従来の言語サービスの自動書式](automatic-formatting-in-a-legacy-language-service.md)
#### [従来の言語サービスのパラメーター ヒント](parameter-info-in-a-legacy-language-service1.md)
#### [従来の言語サービスでのステートメント入力補完](statement-completion-in-a-legacy-language-service.md)
#### [従来の言語サービスでのアウトラインと隠し文字](outlining-and-hidden-text-in-a-legacy-language-service.md)
##### [方法: 従来の言語サービスでのアウトラインのサポート](how-to-support-outlining-in-a-legacy-language-service.md)
##### [方法: 従来の言語サービスでの隠し文字サポートの提供](how-to-provide-hidden-text-support-in-a-legacy-language-service.md)
##### [方法: 従来の言語サービスでのアウトラインの拡張サポートの提供](how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)
#### [デバッグのための言語サービスのサポート](language-service-support-for-debugging.md)
## [従来の言語サービスの実装](implementing-a-legacy-language-service1.md)
### [従来の言語サービスの概要](legacy-language-service-overview.md)
### [言語サービスの実装](implementing-a-legacy-language-service2.md)
### [言語サービスの登録](registering-a-legacy-language-service1.md)
### [従来の言語サービスのパーサーとスキャナー](legacy-language-service-parser-and-scanner.md)
### [チュートリアル: 従来の言語サービスの作成](walkthrough-creating-a-legacy-language-service.md)
### [チュートリアル: インストールされているコード スニペットの一覧の取得 (従来の実装)](walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)
### [従来の言語サービスの特徴](legacy-language-service-features1.md)
#### [従来の言語サービスでのかっこの一致](brace-matching-in-a-legacy-language-service.md)
#### [従来の言語サービスのコメント コード](commenting-code-in-a-legacy-language-service.md)
#### [従来の言語サービスのカスタム ドキュメント プロパティ](custom-document-properties-in-a-legacy-language-service.md)
#### [従来の言語サービスのアウトライン](outlining-in-a-legacy-language-service.md)
#### [従来の言語サービスの再フォーマット コード](reformatting-code-in-a-legacy-language-service.md)
#### [従来の言語サービスでのコード スニペットのサポート](support-for-code-snippets-in-a-legacy-language-service.md)
#### [従来の言語サービスのパラメーター ヒント](parameter-info-in-a-legacy-language-service2.md)
#### [従来の言語サービスのクイック ヒント](quick-info-in-a-legacy-language-service.md)
#### [従来の言語サービスでのメンバー補完](member-completion-in-a-legacy-language-service.md)
#### [従来の言語サービスでの単語補完](word-completion-in-a-legacy-language-service.md)
#### [従来の言語サービスでの自動変数ウィンドウのサポート](support-for-the-autos-window-in-a-legacy-language-service.md)
#### [従来の言語サービスでのナビゲーション バーのサポート](support-for-the-navigation-bar-in-a-legacy-language-service.md)
#### [従来の言語サービスでの構文の配色変更](syntax-colorizing-in-a-legacy-language-service.md)
#### [従来の言語サービスでのブレークポイントの検証](validating-breakpoints-in-a-legacy-language-service.md)
## [シンボル参照ツールのサポート](supporting-symbol-browsing-tools.md)
### [方法: オブジェクト マネージャーを使用したライブラリの登録](how-to-register-a-library-with-the-object-manager.md)
### [方法: ライブラリによって提供されるシンボルのリストをオブジェクト マネージャーに公開する](how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)
### [方法: ライブラリでのシンボルの識別](how-to-identify-symbols-in-a-library.md)
# [プロジェクト](projects.md)
## [新しいプロジェクトの生成: 内部、パート 1](new-project-generation-under-the-hood-part-one.md)
## [新しいプロジェクトの生成: 内部、パート 2](new-project-generation-under-the-hood-part-two.md)
## [プロジェクト タイプ](project-types.md)
### [基本情報](project-type-essentials.md)
### [プロジェクト タイプの作成](creating-project-types.md)
#### [プロジェクト タイプのデザインの方針](project-type-design-decisions.md)
#### [チェック リスト: 新しいプロジェクト タイプの作成](checklist-creating-new-project-types.md)
#### [プロジェクト ファクトリを使用したプロジェクト インスタンスの作成](creating-project-instances-by-using-project-factories.md)
#### [マネージド パッケージ フレームワークを使用したプロジェクト タイプの実装 (C#)](using-the-managed-package-framework-to-implement-a-project-type-csharp.md)
#### [プロジェクト タイプの登録](registering-a-project-type.md)
#### [プロジェクトの永続化](project-persistence.md)
#### [MSBuild の使用](using-msbuild.md)
### [プロジェクト テンプレートとプロジェクト項目テンプレートの追加](adding-project-and-project-item-templates.md)
#### [プロジェクトのコンテキスト](project-context.md)
#### [プロジェクトの優先順位](project-priority.md)
#### [その他のファイル プロジェクト](miscellaneous-files-project.md)
#### [プロジェクトと項目テンプレートの登録](registering-project-and-item-templates.md)
#### [[新しい項目の追加] ダイアログ ボックスへの項目の追加](adding-items-to-the-add-new-item-dialog-boxes.md)
#### [[新しいプロジェクト] ダイアログ ボックスへの新しいディレクトリの追加](adding-directories-to-the-new-project-dialog-box.md)
#### [[新しい項目の追加] ダイアログ ボックスへの新しいディレクトリの追加](adding-directories-to-the-add-new-item-dialog-box.md)
#### [プロジェクト システムを拡張するための IDE 定義コマンド](ide-defined-commands-for-extending-project-systems.md)
#### [プロジェクトの拡張に通常使用されるオブジェクトの CATID](catids-for-objects-that-are-typically-used-to-extend-projects.md)
### [プロジェクト項目のオープンと保存](opening-and-saving-project-items.md)
#### [ファイルを開くコマンドを使用したファイルの表示](displaying-files-by-using-the-open-file-command.md)
#### [プログラムから開くコマンドを使用したファイルの表示](displaying-files-by-using-the-open-with-command.md)
#### [標準ドキュメントの保存](saving-a-standard-document.md)
#### [カスタム ドキュメントの保存](saving-a-custom-document.md)
#### [プロジェクトでのファイルを開くエディターの決定](determining-which-editor-opens-a-file-in-a-project.md)
### [構成オプションの管理](managing-configuration-options.md)
#### [概要](configuration-options-overview.md)
#### [プロパティ ページ](property-pages.md)
#### [ソリューション構成](solution-configuration.md)
#### [プロジェクト構成オブジェクト](project-configuration-object.md)
#### [ビルドのためのプロジェクト構成](project-configuration-for-building.md)
#### [展開の管理のためのプロジェクト構成](project-configuration-for-managing-deployment.md)
#### [出力のためのプロジェクト構成](project-configuration-for-output.md)
### [ソース管理のサポート](supporting-source-control.md)
#### [ソース管理パッケージのモデル](model-for-source-control-packages.md)
#### [設計上の決定事項](source-control-design-decisions.md)
#### [構成の詳細](source-control-configuration-details.md)
#### [プロジェクトとエディターに関する追加のガイドライン](additional-source-control-guidelines-for-projects-and-editors.md)
#### [ランタイムの詳細](source-control-runtime-details.md)
### [入れ子になったプロジェクト](nesting-projects.md)
#### [方法: 入れ子になったプロジェクトの実装](how-to-implement-nested-projects.md)
#### [入れ子になったプロジェクトのアンロードと再ロードに関する考慮事項](considerations-for-unloading-and-reloading-nested-projects.md)
#### [入れ子になったプロジェクト向けのウィザード サポート](wizard-support-for-nested-projects.md)
#### [入れ子になったプロジェクト向けのコマンド処理の実装](implementing-command-handling-for-nested-projects.md)
#### [入れ子になったプロジェクトのための [AddItem] ダイアログ ボックスのフィルター処理](filtering-the-additem-dialog-box-for-nested-projects.md)
### [プロジェクトのアップグレード](upgrading-projects.md)
### [アーキテクチャ](project-types-architecture.md)
#### [プロジェクト モデルの要素](elements-of-a-project-model.md)
#### [プロジェクト モデルのコア コンポーネント](project-model-core-components.md)
#### [プロジェクト タイプを作成する状況](when-to-create-project-types.md)
#### [階層と選択](hierarchies-and-selection.md)
##### [Visual Studio での階層](hierarchies-in-visual-studio.md)
##### [IDE での選択と通貨](selection-and-currency-in-the-ide.md)
##### [コンテキスト オブジェクトの選択](selection-context-objects.md)
##### [ユーザーへのフィードバック](feedback-to-the-user.md)
## [プロジェクト サブタイプ](project-subtypes.md)
### [プロジェクト サブタイプのデザイン](project-subtypes-design.md)
### [プロジェクト サブタイプの初期化シーケンス](initialization-sequence-of-project-subtypes.md)
### [プロジェクト サブタイプによって拡張されるプロパティとメソッド](properties-and-methods-extended-by-project-subtypes.md)
### [MSBuild プロジェクト ファイルでのデータの保持](persisting-data-in-the-msbuild-project-file.md)
### [プロジェクト プロパティのユーザー インターフェイス](project-property-user-interface.md)
### [ベース プロジェクトのオブジェクト モデルの拡張](extending-the-object-model-of-the-base-project.md)
### [[新しい項目の追加] ダイアログ ボックスへの投稿](contributing-to-the-add-new-item-dialog-box.md)
## [Web プロジェクト](web-projects.md)
### [基本情報](web-project-essentials.md)
### [Web サイト サポート](web-site-support.md)
#### [Web サイト サポートのテンプレート](web-site-support-templates.md)
#### [Web サイト サポートの属性](web-site-support-attributes.md)
## [特別な展開の処理](handling-specialized-deployment.md)
## [オートメーション モデルへの投稿](contributing-to-the-automation-model.md)
### [オートメーション モデルの概要](automation-model-overview.md)
### [VSPackage でのオートメーションの提供](providing-automation-for-vspackages.md)
### [プロジェクト オブジェクトの公開](exposing-project-objects.md)
### [プロジェクトのモデリング](project-modeling.md)
### [イベントの公開](exposing-events-in-the-visual-studio-sdk.md)
### [オプション ページのオートメーションのサポート](automation-support-for-options-pages.md)
### [コードのオートメーションの提供](providing-automation-for-code.md)
### [方法: Windows 向けのオートメーションの提供](how-to-provide-automation-for-windows.md)
### [オートメーション モデルの使用](using-the-automation-model.md)
### [構成および SelectedItem オブジェクトのためのオートメーション](automation-for-configuration-and-selecteditem-objects.md)
# [ソリューション](solutions.md)
## [概要](solutions-overview.md)
## [ソリューション (.Sln) ファイル](solution-dot-sln-file.md)
## [ソリューション ユーザー オプション (.Suo) ファイル](solution-user-options-dot-suo-file.md)
# [プロパティの拡張](extending-properties.md)
## [プロパティ ウィンドウの概要](properties-window-overview.md)
## [テンプレート ポリシーとプロパティ ウィンドウ](template-policy-and-the-properties-window.md)
## [プロパティ ウィンドウのフィールドとインターフェイス](properties-window-fields-and-interfaces.md)
## [プロパティ ウィンドウのオブジェクト一覧](properties-window-object-list.md)
## [プロパティ ウィンドウのボタン](properties-window-buttons.md)
## [プロパティ表示グリッド](properties-display-grid.md)
## [プロジェクトおよび構成プロパティのサポート](support-for-project-and-configuration-properties.md)
# [オプションとオプション ページ](options-and-options-pages.md)
## [オプション ページの作成](creating-options-pages.md)
# [サービスの基本情報](service-essentials.md)
## [使用可能なサービスの一覧](list-of-available-services.md)
# [Visual Studio デバッガーの拡張性](../debugger/visual-studio-debugger-extensibility.md)
# [ソース管理](source-control.md)
## [基本情報](source-control-integration-essentials.md)
## [概要](source-control-integration-overview.md)
### [ソース管理の新機能](what-s-new-in-source-control.md)
## [ソース管理プラグインの作成](creating-a-source-control-plug-in.md)
### [はじめに](getting-started-with-source-control-plug-ins.md)
#### [方法: ソース管理プラグインのインストール](how-to-install-a-source-control-plug-in.md)
#### [ソース管理プラグイン API バージョン 1.3 の新機能](what-s-new-in-the-source-control-plug-in-api-version-1-3.md)
#### [ソース管理プラグイン API バージョン 1.2 の新機能](what-s-new-in-the-source-control-plug-in-api-version-1-2.md)
##### [~SAK ファイルの削除](elimination-of-tilde-sak-files.md)
##### [複数のプロジェクト接続全体への設定の適用](application-of-settings-across-multiple-project-connections.md)
##### [ソリューションの親コンテナー フォルダーの作成](creating-parent-container-folders-for-solutions.md)
##### [ソース管理ストアとローカルのプロジェクト フォルダーとの比較 (オプション)](optional-comparison-of-local-project-folder-to-source-control-store.md)
##### [.Proj および .Sln ファイルからのソース管理情報の削除](removal-of-source-control-information-from-dot-proj-and-dot-sln-files.md)
### [アーキテクチャ](source-control-plug-in-architecture.md)
### [ソース管理プラグイン向けのテスト ガイド](test-guide-for-source-control-plug-ins.md)
#### [テスト領域 1: ソース管理への追加とオープン](test-area-1-add-to-open-from-source-control.md)
#### [テスト領域 2: ソース管理からの取得](test-area-2-get-from-source-control.md)
#### [テスト領域 3: チェックアウトとチェックアウトの取り消し](test-area-3-check-out-undo-checkout.md)
#### [テスト領域 4: チェックイン](test-area-4-check-in.md)
#### [テスト領域 5: ソース管理の変更](test-area-5-change-source-control.md)
#### [テスト領域 6: 削除](test-area-6-delete.md)
#### [テスト領域 7: 共有](test-area-7-share.md)
#### [テスト領域 8: プラグインの切り替え](test-area-8-plug-in-switching.md)
## [ソース管理 VSPackage の作成](creating-a-source-control-vspackage.md)
### [はじめに](getting-started-with-source-control-vspackages.md)
#### [ソース管理 VSPackage を実装するかどうかの決定](determining-whether-to-implement-a-source-control-vspackage.md)
### [アーキテクチャ](source-control-vspackage-architecture.md)
### [機能](source-control-vspackage-features.md)
#### [登録と選択](registration-and-selection-source-control-vspackage.md)
#### [クエリの編集とクエリの保存](query-edit-query-save-source-control-vspackage.md)
#### [グリフ管理](glyph-control-source-control-vspackage.md)
#### [カスタム ユーザー インターフェイス](custom-user-interface-source-control-vspackage.md)
### [デザイン要素](source-control-vspackage-design-elements.md)
#### [VSPackage 構造](vspackage-structure-source-control-vspackage.md)
#### [関連サービスとインターフェイス](related-services-and-interfaces-source-control-vspackage.md)
#### [提供されるサービス](services-provided-source-control-vspackage.md)
# [ウィザード](wizards.md)
## [テンプレート ディレクトリの説明 (.Vsdir) ファイル](template-directory-description-dot-vsdir-files.md)
## [ウィザード (.Vsz) ファイル](wizard-dot-vsz-file.md)
## [ウィザード インターフェイス (IDTWizard)](wizard-interface-idtwizard.md)
## [コンテキスト パラメーター](context-parameters.md)
## [カスタム パラメーター](custom-parameters.md)
# [カスタム ツール](custom-tools.md)
## [単一ファイル ジェネレーターの実装](implementing-single-file-generators.md)
## [単一ファイル ジェネレーターの登録](registering-single-file-generators.md)
## [ビジュアル デザイナーへのタイプの公開](exposing-types-to-visual-designers.md)
# [VSSDK ユーティリティ](vssdk-utilities.md)
## [RegPkg ユーティリティ](regpkg-utility.md)
### [RegPkg パッケージ登録のトラブルシューティング](troubleshooting-regpkg-package-registration.md)
## [CreatePkgDef ユーティリティ](createpkgdef-utility.md)
## [CreateExpInstance ユーティリティ](createexpinstance-utility.md)
## [カラー テーマのツール](color-theming-tools.md)
### [VSIX カラー エディター](vsix-color-editor.md)
### [VSIX カラー コンパイラ](vsix-color-compiler.md)
## [イメージ サービスのツール](image-service-tools.md)
### [リソースからのマニフェスト](manifest-from-resources.md)
### [コードへのマニフェスト](manifest-to-code.md)
### [イメージ ライブラリ ビューア](image-library-viewer.md)
# [Windows インストーラーによる VSPackage のインストール](installing-vspackages-with-windows-installer.md)
## [Windows インストーラーの基本事項](windows-installer-basics.md)
## [VSPackage のセットアップ シナリオ](vspackage-setup-scenarios.md)
## [Windows インストーラー パッケージの編集](authoring-a-windows-installer-package.md)
## [システム要件の検出](detecting-system-requirements.md)
## [コンポーネント管理](component-management.md)
## [VSPackage のインストール ディレクトリの選択](choosing-the-installation-directory-for-a-vspackage.md)
## [VSPackage の登録](vspackage-registration.md)
## [プロジェクト タイプの配置](deploying-project-types.md)
## [方法: インストーラー向けの登録情報の生成](how-to-generate-registry-information-for-an-installer.md)
## [インストール後に実行する必要があるコマンド](commands-that-must-be-run-after-installation.md)
## [Windows インストーラーによる VSPackage のアンインストール](uninstalling-a-vspackage-with-windows-installer.md)
