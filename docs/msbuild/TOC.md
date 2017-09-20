# [MSBuild](msbuild.md)

## [MSBuild 15.0 の新機能](what-s-new-in-msbuild-15-0.md)

## [MSBuild の概念](msbuild-concepts.md)

### [MSBuild プロパティ](msbuild-properties.md)

#### [方法: ビルドで環境変数を使用する](how-to-use-environment-variables-in-a-build.md)

#### [方法: プロジェクト ファイルの名前または場所を参照する](how-to-reference-the-name-or-location-of-the-project-file.md)

#### [方法: 同じソース ファイルを異なるオプションでビルドする](how-to-build-the-same-source-files-with-different-options.md)

#### [プロパティ関数](property-functions.md)

### [MSBuild 項目](msbuild-items.md)

#### [方法: ビルドするファイルを選択する](how-to-select-the-files-to-build.md)

#### [方法: ビルドからファイルを除外する](how-to-exclude-files-from-the-build.md)

#### [方法: 項目リストをコンマ区切りで表示する](how-to-display-an-item-list-separated-with-commas.md)

#### [項目定義](item-definitions.md)

#### [項目用の関数](item-functions.md)

#### [ファイルの追跡](file-tracking.md)

##### [EndTrackingContext](endtrackingcontext.md)

##### [ResumeTracking](resumetracking.md)

##### [SetThreadCount](setthreadcount.md)

##### [StartTrackingContext](starttrackingcontext.md)

##### [StartTrackingContextWithRoot](starttrackingcontextwithroot.md)

##### [StopTrackingAndCleanup](stoptrackingandcleanup.md)

##### [SuspendTracking](suspendtracking.md)

##### [WriteAllTLogs](writealltlogs.md)

##### [WriteContextTLogs](writecontexttlogs.md)

### [MSBuild ターゲット](msbuild-targets.md)

#### [ターゲットのビルド順序](target-build-order.md)

#### [インクリメンタル ビルド](incremental-builds.md)

#### [方法: 最初にビルドするターゲットを指定する](how-to-specify-which-target-to-build-first.md)

#### [方法: 複数のプロジェクト ファイルで同じターゲットを使用する](how-to-use-the-same-target-in-multiple-project-files.md)

#### [方法: MSBuild.exe を使用してソリューション内の特定のターゲットをビルドする](how-to-build-specific-targets-in-solutions-by-using-msbuild-exe.md)

#### [方法: インクリメンタル ビルドを実行する](how-to-build-incrementally.md)

#### [方法: ビルドをクリーンする](how-to-clean-a-build.md)

### [MSBuild タスク](msbuild-tasks.md)

#### [タスクの作成](task-writing.md)

#### [方法: タスクで発生したエラーを無視する](how-to-ignore-errors-in-tasks.md)

#### [方法: リソースがあるプロジェクトをビルドする](how-to-build-a-project-that-has-resources.md)

#### [MSBuild インライン タスク](msbuild-inline-tasks.md)

##### [チュートリアル: インライン タスクの作成](walkthrough-creating-an-inline-task.md)

### [プロパティと項目の比較](comparing-properties-and-items.md)

### [MSBuild の特殊文字](msbuild-special-characters.md)

#### [方法: MSBuild で特殊文字をエスケープする](how-to-escape-special-characters-in-msbuild.md)

#### [方法: 予約済みの XML 文字をプロジェクト ファイルで使用する](how-to-use-reserved-xml-characters-in-project-files.md)

## [MSBuild の詳細な概念](msbuild-advanced-concepts.md)

### [MSBuild バッチ](msbuild-batching.md)

#### [タスクのバッチの項目メタデータ](item-metadata-in-task-batching.md)

#### [ターゲットのバッチの項目メタデータ](item-metadata-in-target-batching.md)

### [MSBuild 変換](msbuild-transforms.md)

### [Visual Studio の統合 (MSBuild)](visual-studio-integration-msbuild.md)

#### [方法: Visual Studio ビルド処理を拡張する](how-to-extend-the-visual-studio-build-process.md)

#### [IDE 内からのビルドの開始](starting-a-build-from-within-the-ide.md)

#### [.NET Framework の拡張機能の登録](registering-extensions-of-the-dotnet-framework.md)

### [MSBuild での複数のプロジェクトの並行ビルド](building-multiple-projects-in-parallel-with-msbuild.md)

#### [複数のプロセッサを使用したプロジェクトのビルド](using-multiple-processors-to-build-projects.md)

#### [大規模なプロジェクトのビルドにおけるメモリの効率的な使用](using-memory-efficiently-when-you-build-large-projects.md)

### [MSBuild のマルチターゲットの概要](msbuild-multitargeting-overview.md)

#### [MSBuild ツールセット (ToolsVersion)](msbuild-toolset-toolsversion.md)

##### [標準ツールセット構成とカスタム ツールセット構成](standard-and-custom-toolset-configurations.md)

##### [ToolsVersion 設定のオーバーライド](overriding-toolsversion-settings.md)

#### [MSBuild ターゲット フレームワークおよびターゲット プラットフォーム](msbuild-target-framework-and-target-platform.md)

#### [デザイン時のアセンブリの解決](resolving-assemblies-at-design-time.md)

#### [ターゲットとタスクの構成](configuring-targets-and-tasks.md)

##### [方法: ターゲットとタスクを構成する](how-to-configure-targets-and-tasks.md)

#### [.NET Framework を対象とするエラーのトラブルシューティング](troubleshooting-dotnet-framework-targeting-errors.md)

### [ビルドのカスタマイズ](customize-your-build.md)

### [MSBuild のベスト プラクティス](msbuild-best-practices.md)

## [MSBuild でのログ](logging-in-msbuild.md)

### [MSBuild でのビルド ログの取得](obtaining-build-logs-with-msbuild.md)

### [ビルド ロガー](build-loggers.md)

### [マルチプロセッサ環境でのログ](logging-in-a-multi-processor-environment.md)

### [マルチプロセッサ対応の logger の記述](writing-multi-processor-aware-loggers.md)

### [転送 logger の作成](creating-forwarding-loggers.md)

## [チュートリアル: MSBuild の使用](walkthrough-using-msbuild.md)

## [チュートリアル: MSBuild プロジェクト ファイルのゼロからの作成](walkthrough-creating-an-msbuild-project-file-from-scratch.md)

## [MSBuild リファレンス](msbuild-reference.md)

### [MSBuild プロジェクト ファイル スキーマ リファレンス](msbuild-project-file-schema-reference.md)

#### [Choose 要素 (MSBuild)](choose-element-msbuild.md)

#### [Import 要素 (MSBuild)](import-element-msbuild.md)

#### [ImportGroup 要素](importgroup-element.md)

#### [Item 要素 (MSBuild)](item-element-msbuild.md)

#### [ItemDefinitionGroup 要素 (MSBuild)](itemdefinitiongroup-element-msbuild.md)

#### [ItemGroup 要素 (MSBuild)](itemgroup-element-msbuild.md)

#### [ItemMetadata 要素 (MSBuild)](itemmetadata-element-msbuild.md)

#### [OnError 要素 (MSBuild)](onerror-element-msbuild.md)

#### [Otherwise 要素 (MSBuild)](otherwise-element-msbuild.md)

#### [Output 要素 (MSBuild)](output-element-msbuild.md)

#### [Parameter 要素](parameter-element.md)

#### [ParameterGroup 要素](parametergroup-element.md)

#### [Project 要素 (MSBuild)](project-element-msbuild.md)

#### [ProjectExtensions 要素 (MSBuild)](projectextensions-element-msbuild.md)

#### [Property 要素 (MSBuild)](property-element-msbuild.md)

#### [PropertyGroup 要素 (MSBuild)](propertygroup-element-msbuild.md)

#### [Target 要素 (MSBuild)](target-element-msbuild.md)

#### [Task 要素 (MSBuild)](task-element-msbuild.md)

#### [TaskBody 要素 (MSBuild)](taskbody-element-msbuild.md)

#### [UsingTask 要素 (MSBuild)](usingtask-element-msbuild.md)

#### [When 要素 (MSBuild)](when-element-msbuild.md)

### [MSBuild タスク リファレンス](msbuild-task-reference.md)

#### [Visual C++ に固有の MSBuild タスク](msbuild-tasks-specific-to-visual-cpp.md)

##### [BscMake タスク](bscmake-task.md)

##### [CL タスク](cl-task.md)

##### [CPPClean タスク](cppclean-task.md)

##### [LIB タスク](lib-task.md)

##### [Link タスク](link-task.md)

##### [MIDL タスク](midl-task.md)

##### [MT タスク](mt-task.md)

##### [RC タスク](rc-task.md)

##### [SetEnv タスク](setenv-task.md)

##### [VCMessage タスク](vcmessage-task.md)

##### [XDCMake タスク](xdcmake-task.md)

##### [XSD タスク](xsd-task.md)

#### [Task 基本クラス](task-base-class.md)

#### [TaskExtension 基本クラス](taskextension-base-class.md)

#### [ToolTaskExtension 基本クラス](tooltaskextension-base-class.md)

#### [AL (アセンブリ リンカー) タスク](al-assembly-linker-task.md)

#### [AspNetCompiler タスク](aspnetcompiler-task.md)

#### [AssignCulture タスク](assignculture-task.md)

#### [AssignProjectConfiguration タスク](assignprojectconfiguration-task.md)

#### [AssignTargetPath タスク](assigntargetpath-task.md)

#### [CallTarget タスク](calltarget-task.md)

#### [CombinePath タスク](combinepath-task.md)

#### [ConvertToAbsolutePath タスク](converttoabsolutepath-task.md)

#### [Copy タスク](copy-task.md)

#### [CreateCSharpManifestResourceName タスク](createcsharpmanifestresourcename-task.md)

#### [CreateItem タスク](createitem-task.md)

#### [CreateProperty タスク](createproperty-task.md)

#### [CreateVisualBasicManifestResourceName タスク](createvisualbasicmanifestresourcename-task.md)

#### [Csc タスク](csc-task.md)

#### [Delete タスク](delete-task.md)

#### [Error タスク](error-task.md)

#### [Exec タスク](exec-task.md)

#### [FindAppConfigFile タスク](findappconfigfile-task.md)

#### [FindInList タスク](findinlist-task.md)

#### [FindUnderPath タスク](findunderpath-task.md)

#### [FormatUrl タスク](formaturl-task.md)

#### [FormatVersion タスク](formatversion-task.md)

#### [GenerateApplicationManifest タスク](generateapplicationmanifest-task.md)

#### [GenerateBootstrapper タスク](generatebootstrapper-task.md)

#### [GenerateDeploymentManifest タスク](generatedeploymentmanifest-task.md)

#### [GenerateResource タスク](generateresource-task.md)

#### [GenerateTrustInfo タスク](generatetrustinfo-task.md)

#### [GetAssemblyIdentity タスク](getassemblyidentity-task.md)

#### [GetFrameworkPath タスク](getframeworkpath-task.md)

#### [GetFrameworkSdkPath タスク](getframeworksdkpath-task.md)

#### [GetReferenceAssemblyPaths タスク](getreferenceassemblypaths-task.md)

#### [LC タスク](lc-task.md)

#### [MakeDir タスク](makedir-task.md)

#### [Message タスク](message-task.md)

#### [Move タスク](move-task.md)

#### [MSBuild タスク](msbuild-task.md)

#### [ReadLinesFromFile タスク](readlinesfromfile-task.md)

#### [RegisterAssembly タスク](registerassembly-task.md)

#### [RemoveDir タスク](removedir-task.md)

#### [RemoveDuplicates タスク](removeduplicates-task.md)

#### [RequiresFramework35SP1Assembly タスク](requiresframework35sp1assembly-task.md)

#### [ResolveAssemblyReference タスク](resolveassemblyreference-task.md)

#### [ResolveCOMReference タスク](resolvecomreference-task.md)

#### [ResolveKeySource タスク](resolvekeysource-task.md)

#### [ResolveManifestFiles タスク](resolvemanifestfiles-task.md)

#### [ResolveNativeReference タスク](resolvenativereference-task.md)

#### [ResolveNonMSBuildProjectOutput タスク](resolvenonmsbuildprojectoutput-task.md)

#### [SGen タスク](sgen-task.md)

#### [SignFile タスク](signfile-task.md)

#### [Touch タスク](touch-task.md)

#### [UnregisterAssembly タスク](unregisterassembly-task.md)

#### [UpdateManifest タスク](updatemanifest-task.md)

#### [Vbc タスク](vbc-task.md)

#### [Warning タスク](warning-task.md)

#### [WriteCodeFragment タスク](writecodefragment-task.md)

#### [WriteLinesToFile タスク](writelinestofile-task.md)

#### [XmlPeek タスク](xmlpeek-task.md)

#### [XmlPoke タスク](xmlpoke-task.md)

#### [XslTransformation タスク](xsltransformation-task.md)

### [MSBuild の条件](msbuild-conditions.md)

### [MSBuild の条件構造](msbuild-conditional-constructs.md)

### [MSBuild の予約済みおよび既知のプロパティ](msbuild-reserved-and-well-known-properties.md)

### [MSBuild プロジェクトの共通プロパティ](common-msbuild-project-properties.md)

### [MSBuild プロジェクトの共通項目](common-msbuild-project-items.md)

### [MSBuild コマンド ライン リファレンス](msbuild-command-line-reference.md)

### [MSBuild .Targets ファイル](msbuild-dot-targets-files.md)

### [MSBuild 既知のアイテム メタデータ](msbuild-well-known-item-metadata.md)

### [MSBuild 応答ファイル](msbuild-response-files.md)

### [WPF MSBuild Reference (WPF MSBuild リファレンス)](wpf-msbuild-reference.md)

#### [WPF .Targets ファイル](wpf-dot-targets-files.md)

#### [WPF MSBuild タスク リファレンス](wpf-msbuild-task-reference.md)

##### [FileClassifier タスク](fileclassifier-task.md)

##### [GenerateTemporaryTargetAssembly タスク](generatetemporarytargetassembly-task.md)

##### [GetWinFXPath タスク](getwinfxpath-task.md)

##### [MarkupCompilePass1 タスク](markupcompilepass1-task.md)

##### [MarkupCompilePass2 タスク](markupcompilepass2-task.md)

##### [MergeLocalizationDirectives タスク](mergelocalizationdirectives-task.md)

##### [ResourcesGenerator タスク](resourcesgenerator-task.md)

##### [UidManager タスク](uidmanager-task.md)

##### [UpdateManifestForBrowserApplication タスク](updatemanifestforbrowserapplication-task.md)

### [特殊文字のエスケープ](special-characters-to-escape.md)

## [MSBuild 用語集](msbuild-glossary.md)
