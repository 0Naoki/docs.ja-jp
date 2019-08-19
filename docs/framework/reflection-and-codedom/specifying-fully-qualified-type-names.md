---
title: 完全修飾型名の指定
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc8395492992c22da3c635f0de010516127f9be4
ms.sourcegitcommit: 46c68557bf6395f0ab9915f7558f2faae0097695
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2019
ms.locfileid: "61793004"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="ffb54-102">完全修飾型名の指定</span><span class="sxs-lookup"><span data-stu-id="ffb54-102">Specifying fully qualified type names</span></span>

<span data-ttu-id="ffb54-103">多様なリフレクション操作に対して有効な入力の型名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffb54-103">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="ffb54-104">完全修飾型名は、アセンブリ名の指定、名前空間の指定、および型名で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-104">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="ffb54-105">型名の指定は、<xref:System.Type.GetType%2A?displayProperty=nameWithType>、<xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>、<xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>、<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> などのメソッドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-105">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>

## <a name="grammar-for-type-names"></a><span data-ttu-id="ffb54-106">型名の文法</span><span class="sxs-lookup"><span data-stu-id="ffb54-106">Grammar for type names</span></span>

 <span data-ttu-id="ffb54-107">文法で正式な言語の構文が定義されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-107">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="ffb54-108">次の表は、有効な入力を認識する方法を示す構文規則の一覧です。</span><span class="sxs-lookup"><span data-stu-id="ffb54-108">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="ffb54-109">終端要素 (これ以上は単純化できない要素) はすべて大文字で記載しています。</span><span class="sxs-lookup"><span data-stu-id="ffb54-109">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="ffb54-110">非終端要素 (これ以上単純化することができる要素) は、大文字と小文字の混在、または単一引用符で囲まれた文字列で記載していますが、単一引用符 (') 自体は構文の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="ffb54-110">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="ffb54-111">パイプ文字 (&#124;) は、サブ規則がある規則を示します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-111">The pipe character (&#124;) denotes rules that have subrules.</span></span>

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a><span data-ttu-id="ffb54-112">特殊文字の指定</span><span class="sxs-lookup"><span data-stu-id="ffb54-112">Specifying special characters</span></span>

<span data-ttu-id="ffb54-113">型名の IDENTIFIER は、言語の規則で決められた任意の有効な名前です。</span><span class="sxs-lookup"><span data-stu-id="ffb54-113">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>

<span data-ttu-id="ffb54-114">IDENTIFIER の一部として使用する場合、次のトークンを区切るには、エスケープ文字としてバックスラッシュ (\\) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-114">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>

|<span data-ttu-id="ffb54-115">トークン</span><span class="sxs-lookup"><span data-stu-id="ffb54-115">Token</span></span>|<span data-ttu-id="ffb54-116">説明</span><span class="sxs-lookup"><span data-stu-id="ffb54-116">Meaning</span></span>|
|-----------|-------------|
|<span data-ttu-id="ffb54-117">\\、</span><span class="sxs-lookup"><span data-stu-id="ffb54-117">\\,</span></span>|<span data-ttu-id="ffb54-118">アセンブリの区切り文字。</span><span class="sxs-lookup"><span data-stu-id="ffb54-118">Assembly separator.</span></span>|
|\\+|<span data-ttu-id="ffb54-119">入れ子にされた型の区切り文字。</span><span class="sxs-lookup"><span data-stu-id="ffb54-119">Nested type separator.</span></span>|
|\\&|<span data-ttu-id="ffb54-120">参照型。</span><span class="sxs-lookup"><span data-stu-id="ffb54-120">Reference type.</span></span>|
|\\*|<span data-ttu-id="ffb54-121">ポインター型。</span><span class="sxs-lookup"><span data-stu-id="ffb54-121">Pointer type.</span></span>|
|<span data-ttu-id="ffb54-122">\\[</span><span class="sxs-lookup"><span data-stu-id="ffb54-122">\\[</span></span>|<span data-ttu-id="ffb54-123">配列次元の区切り文字。</span><span class="sxs-lookup"><span data-stu-id="ffb54-123">Array dimension delimiter.</span></span>|
|<span data-ttu-id="ffb54-124">\\]</span><span class="sxs-lookup"><span data-stu-id="ffb54-124">\\]</span></span>|<span data-ttu-id="ffb54-125">配列次元の区切り文字。</span><span class="sxs-lookup"><span data-stu-id="ffb54-125">Array dimension delimiter.</span></span>|
|<span data-ttu-id="ffb54-126">\\。</span><span class="sxs-lookup"><span data-stu-id="ffb54-126">\\.</span></span>|<span data-ttu-id="ffb54-127">配列の指定内にピリオドを使用する場合にのみ、ピリオドの前にバックスラッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-127">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="ffb54-128">NamespaceSpec 内のピリオドにはバックスラッシュを使用できません。</span><span class="sxs-lookup"><span data-stu-id="ffb54-128">Periods in NamespaceSpec do not take the backslash.</span></span>|
|<span data-ttu-id="ffb54-129">\\\|文字列リテラルとして必要な場合のバックスラッシュ。</span><span class="sxs-lookup"><span data-stu-id="ffb54-129">\\\|Backslash when needed as a string literal.</span></span>|

<span data-ttu-id="ffb54-130">AssemblyNameSpec を除くすべての TypeSpec コンポーネントで、スペースは関係があります。</span><span class="sxs-lookup"><span data-stu-id="ffb54-130">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="ffb54-131">AssemblyNameSpec の場合、',' 区切り文字の前にあるスペースは関係がありますが、',' の後のスペースは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-131">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>

<span data-ttu-id="ffb54-132"><xref:System.Type.FullName%2A?displayProperty=nameWithType> などのリフレクション クラスは、`MyType.GetType(myType.FullName)` と同様に返される名前を <xref:System.Type.GetType%2A> の呼び出しに使用できるように、壊れた名前を返します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-132">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>

<span data-ttu-id="ffb54-133">たとえば、型の完全修飾型名が `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly` だとします。</span><span class="sxs-lookup"><span data-stu-id="ffb54-133">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>

<span data-ttu-id="ffb54-134">名前空間が `Ozzy.Out+Back` の場合、プラス記号の前にはバックスラッシュを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffb54-134">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="ffb54-135">そうしないと、パーサーから入れ子の区切り文字として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-135">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="ffb54-136">リフレクションからこの文字列は `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly` として出力されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-136">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>

## <a name="specifying-assembly-names"></a><span data-ttu-id="ffb54-137">アセンブリ名の指定</span><span class="sxs-lookup"><span data-stu-id="ffb54-137">Specifying assembly names</span></span>

<span data-ttu-id="ffb54-138">アセンブリ名の指定に必要な最小限の情報は、アセンブリのテキスト形式の名前 (IDENTIFIER) です。</span><span class="sxs-lookup"><span data-stu-id="ffb54-138">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="ffb54-139">次の表で説明されているプロパティ/値ペアのコンマ区切りの一覧で、IDENTIFIER に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-139">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="ffb54-140">IDENTIFIER の名前付けは、ファイルの名前付け規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffb54-140">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="ffb54-141">IDENTIFIER は大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="ffb54-141">The IDENTIFIER is case-insensitive.</span></span>

|<span data-ttu-id="ffb54-142">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="ffb54-142">Property name</span></span>|<span data-ttu-id="ffb54-143">説明</span><span class="sxs-lookup"><span data-stu-id="ffb54-143">Description</span></span>|<span data-ttu-id="ffb54-144">使用できる値</span><span class="sxs-lookup"><span data-stu-id="ffb54-144">Allowable values</span></span>|
|-------------------|-----------------|----------------------|
|<span data-ttu-id="ffb54-145">**Version**</span><span class="sxs-lookup"><span data-stu-id="ffb54-145">**Version**</span></span>|<span data-ttu-id="ffb54-146">アセンブリのバージョン番号</span><span class="sxs-lookup"><span data-stu-id="ffb54-146">Assembly version number</span></span>|<span data-ttu-id="ffb54-147">*Major.Minor.Build.Revision*。*Major*、*Minor*、*Build*、*Revision* は 0 以上 65535 以下の整数です。</span><span class="sxs-lookup"><span data-stu-id="ffb54-147">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|
|<span data-ttu-id="ffb54-148">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="ffb54-148">**PublicKey**</span></span>|<span data-ttu-id="ffb54-149">完全な公開鍵</span><span class="sxs-lookup"><span data-stu-id="ffb54-149">Full public key</span></span>|<span data-ttu-id="ffb54-150">16 進数形式の完全な公開鍵の文字列値。</span><span class="sxs-lookup"><span data-stu-id="ffb54-150">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="ffb54-151">プライベート アセンブリを明示的に指定するには、null 参照を指定します (Visual Basic では **Nothing**)。</span><span class="sxs-lookup"><span data-stu-id="ffb54-151">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="ffb54-152">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="ffb54-152">**PublicKeyToken**</span></span>|<span data-ttu-id="ffb54-153">公開鍵トークン (完全な公開鍵の 8 バイト ハッシュ)</span><span class="sxs-lookup"><span data-stu-id="ffb54-153">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="ffb54-154">16 進数形式の公開鍵トークンの文字列値。</span><span class="sxs-lookup"><span data-stu-id="ffb54-154">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="ffb54-155">プライベート アセンブリを明示的に指定するには、null 参照を指定します (Visual Basic では **Nothing**)。</span><span class="sxs-lookup"><span data-stu-id="ffb54-155">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="ffb54-156">**カルチャ**</span><span class="sxs-lookup"><span data-stu-id="ffb54-156">**Culture**</span></span>|<span data-ttu-id="ffb54-157">アセンブリのカルチャ</span><span class="sxs-lookup"><span data-stu-id="ffb54-157">Assembly culture</span></span>|<span data-ttu-id="ffb54-158">RFC 1766 形式のアセンブリのカルチャ。言語に依存しない (非サテライト) アセンブリの場合は "neutral"。</span><span class="sxs-lookup"><span data-stu-id="ffb54-158">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|
|<span data-ttu-id="ffb54-159">**カスタム**</span><span class="sxs-lookup"><span data-stu-id="ffb54-159">**Custom**</span></span>|<span data-ttu-id="ffb54-160">カスタム バイナリ ラージ オブジェクト (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="ffb54-160">Custom binary large object (BLOB).</span></span> <span data-ttu-id="ffb54-161">現在、 [Native Image Generator (Ngen)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) で生成されたアセンブリでのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="ffb54-161">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="ffb54-162">アセンブリがインストールされていることをアセンブリ キャッシュに通知するために Native Image Generator ツールに使用されているカスタム文字列は、ネイティブ イメージです。そのため、ネイティブ イメージ キャッシュにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-162">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="ffb54-163">zap 文字列とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-163">Also called a zap string.</span></span>|

<span data-ttu-id="ffb54-164">次に、カルチャが既定で単純な名前のアセンブリの**AssemblyName** の例を示します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-164">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>

```csharp
com.microsoft.crypto, Culture=""
```

<span data-ttu-id="ffb54-165">次に、カルチャが "en" の厳密な名前のアセンブリに対する完全に指定された参照の例を示します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-165">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

<span data-ttu-id="ffb54-166">次の各例は、部分的に指定された **AssemblyName** を示しています。これは厳密な名前または単純な名前のアセンブリで満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-166">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

<span data-ttu-id="ffb54-167">次の各例は、部分的に指定された **AssemblyName** を示しています。これは簡易な名前のアセンブリで満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffb54-167">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

<span data-ttu-id="ffb54-168">次の各例は、部分的に指定された **AssemblyName** を示しています。これは厳密な名前のアセンブリで満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffb54-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a><span data-ttu-id="ffb54-169">ジェネリック型の指定</span><span class="sxs-lookup"><span data-stu-id="ffb54-169">Specifying generic types</span></span>

<span data-ttu-id="ffb54-170">SimpleTypeSpec\`NUMBER は、ジェネリック型パラメーター が 1 ～ *n* であるオープン ジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-170">SimpleTypeSpec\`NUMBER represents an open generic type with from 1 to *n* generic type parameters.</span></span> <span data-ttu-id="ffb54-171">たとえば、オープン ジェネリック型 List\<T> またはクローズ ジェネリック型 List\<String> に対する参照を取得するには、``Type.GetType("System.Collections.Generic.List`1")`` を使用します。ジェネリック型 Dictionary\<TKey,TValue> に対する参照を取得するには、``Type.GetType("System.Collections.Generic.Dictionary`2")`` を使用します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-171">For example, to get reference to the open generic type List\<T> or the closed generic type List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")`` To get a reference to the generic type Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span></span>

## <a name="specifying-pointers"></a><span data-ttu-id="ffb54-172">ポインターの指定</span><span class="sxs-lookup"><span data-stu-id="ffb54-172">Specifying pointers</span></span>

<span data-ttu-id="ffb54-173">SimpleTypeSpec\* はアンマネージ ポインターを示します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-173">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="ffb54-174">たとえば、型 MyType に対するポインターを取得するには、`Type.GetType("MyType*")` を使用します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-174">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="ffb54-175">型 MyType のポインターに対するポインターを取得するには、`Type.GetType("MyType**")` を使用します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-175">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>

## <a name="specifying-references"></a><span data-ttu-id="ffb54-176">参照の指定</span><span class="sxs-lookup"><span data-stu-id="ffb54-176">Specifying references</span></span>

<span data-ttu-id="ffb54-177">SimpleTypeSpec &amp; はマネージド ポインターまたは参照を表します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-177">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="ffb54-178">たとえば、型 MyType に対する参照を取得するには、`Type.GetType("MyType &")` を使用します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-178">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="ffb54-179">ポインターとは異なり、参照は 1 つのレベルに制限されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-179">Note that unlike pointers, references are limited to one level.</span></span>

## <a name="specifying-arrays"></a><span data-ttu-id="ffb54-180">配列の指定</span><span class="sxs-lookup"><span data-stu-id="ffb54-180">Specifying arrays</span></span>

<span data-ttu-id="ffb54-181">BNF 文法では、ReflectionEmitDimension は <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> を使用して取得された不完全な型定義にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-181">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ffb54-182">不完全な型定義とは、<xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> で呼び出されていない、<xref:System.Reflection.Emit?displayProperty=nameWithType> を使用して構築された <xref:System.Reflection.Emit.TypeBuilder> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ffb54-182">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="ffb54-183">ReflectionDimension を使用して、完了している任意の型定義 (読み込まれている型) を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-183">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>

<span data-ttu-id="ffb54-184">配列のランクを指定して、リフレクションで配列にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ffb54-184">Arrays are accessed in reflection by specifying the rank of the array:</span></span>

- <span data-ttu-id="ffb54-185">`Type.GetType("MyArray[]")` は 0 個の下限がある 1 次元配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-185">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>

- <span data-ttu-id="ffb54-186">`Type.GetType("MyArray[*]")` は不明な下限がある 1 次元配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-186">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>
- <span data-ttu-id="ffb54-187">`Type.GetType("MyArray[][]")` は 2 次元配列の配列です。</span><span class="sxs-lookup"><span data-stu-id="ffb54-187">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>

- <span data-ttu-id="ffb54-188">`Type.GetType("MyArray[*,*]")` と `Type.GetType("MyArray[,]")` は、下限が不明な四角形の 2 次元配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="ffb54-188">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>

<span data-ttu-id="ffb54-189">ランタイムの観点からは、多次元配列を別にすれば、`MyArray[] != MyArray[*]` の 2 つの表記は同等です。</span><span class="sxs-lookup"><span data-stu-id="ffb54-189">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="ffb54-190">つまり、`Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` は **true** と評価されます。</span><span class="sxs-lookup"><span data-stu-id="ffb54-190">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>

<span data-ttu-id="ffb54-191">**ModuleBuilder.GetType** の場合、`MyArray[0..5]` はサイズが 6 で下限が 0 の 1 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="ffb54-191">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="ffb54-192">`MyArray[4…]` は、不明なサイズで下限が 4 の 1 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="ffb54-192">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffb54-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffb54-193">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ffb54-194">型情報の表示</span><span class="sxs-lookup"><span data-stu-id="ffb54-194">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)
