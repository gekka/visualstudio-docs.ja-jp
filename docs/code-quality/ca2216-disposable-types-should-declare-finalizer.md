---
title: 'CA2216: 破棄できる型ではファイナライザーを宣言します'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DisposableTypesShouldDeclareFinalizer
- CA2216
helpviewer_keywords:
- CA2216
- DisposableTypesShouldDeclareFinalizer
ms.assetid: 0cabcc5e-b526-452b-8c2a-0cbe3b93c0ef
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9362d7aea5f66be7a7faa237ab1f78853ac7fd6f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549299"
---
# <a name="ca2216-disposable-types-should-declare-finalizer"></a>CA2216: 破棄できる型ではファイナライザーを宣言します

|||
|-|-|
|TypeName|DisposableTypesShouldDeclareFinalizer|
|CheckId|CA2216|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

実装する型<xref:System.IDisposable?displayProperty=fullName>、およびアンマネージ リソースの使用を提案するフィールドを持つ、による記述では、ファイナライザーを実装しません<xref:System.Object.Finalize%2A?displayProperty=fullName>します。

## <a name="rule-description"></a>規則の説明

破棄可能な型には、次の種類のフィールドが含まれている場合は、この規則違反が報告されます。

- <xref:System.IntPtr?displayProperty=fullName>

- <xref:System.UIntPtr?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法

このルールの違反を修正するには、実装を呼び出すファイナライザー、<xref:System.IDisposable.Dispose%2A>メソッド。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

型が実装していない場合、この規則による警告を抑制するのには安全では<xref:System.IDisposable>アンマネージ リソースを解放するためにします。

## <a name="example"></a>例

次の例では、この規則に違反する型を示します。

[!code-csharp[FxCop.Usage.DisposeNoFinalize#1](../code-quality/codesnippet/CSharp/ca2216-disposable-types-should-declare-finalizer_1.cs)]

## <a name="related-rules"></a>関連するルール

[CA2115: ネイティブ リソースを使用しているときには GC.KeepAlive を呼び出します](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

[CA1816: GC.SuppressFinalize を正しく呼び出します](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

[CA1049: ネイティブ リソースを所有する型は、破棄可能でなければなりません](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)

## <a name="see-also"></a>関連項目

- <xref:System.IDisposable?displayProperty=fullName>
- <xref:System.IntPtr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>
- <xref:System.UIntPtr?displayProperty=fullName>
- <xref:System.Object.Finalize%2A?displayProperty=fullName>
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)