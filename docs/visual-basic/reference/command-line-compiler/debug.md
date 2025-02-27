---
title: /debug (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 27485cda9bb2af980b300180134fd7e99ffceeba
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775686"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)

コンパイラによってデバッグ情報が生成され、出力ファイルに配置されます。

## <a name="syntax"></a>構文

```console
-debug[+ | -]
```

、または

```console
-debug:[full | pdbonly]
```

## <a name="arguments"></a>引数

|用語|定義|
|---|---|
|`+` &#124; `-`|省略可能です。 @No__t_0 または `/debug` を指定すると、コンパイラによってデバッグ情報が生成され、.pdb ファイルに配置されます。 @No__t_0 を指定すると、`/debug` を指定しない場合と同じ効果があります。|
|`full` &#124; `pdbonly`|省略可能です。 コンパイラによって生成されるデバッグ情報の種類を指定します。 @No__t_0 を指定しない場合、既定値は `full` になります。これにより、実行中のプログラムにデバッガーをアタッチできます。 @No__t_0 引数を使用すると、プログラムがデバッガーで開始されたときにソースコードのデバッグが可能になりますが、実行中のプログラムがデバッガーにアタッチされている場合にのみ、アセンブリ言語コードが表示されます。|

## <a name="remarks"></a>Remarks

このオプションを使用してデバッグ ビルドを作成します。 @No__t_0、`/debug+`、または `/debug:full` を指定しない場合は、プログラムの出力ファイルをデバッグできません。

既定では、デバッグ情報は出力されません (`/debug-`)。 デバッグ情報を生成するには、`/debug` または `/debug+` を指定します。

アプリケーションのデバッグ パフォーマンスを構成する方法については、「[イメージのデバッグの簡略化](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md)」を参照してください。

|Visual Studio 統合開発環境で-debug を設定するには|
|---|
|1.**ソリューションエクスプローラー**でプロジェクトを選択した状態で、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。 <br />2. **[コンパイル]** タブをクリックします。<br />3. **[詳細コンパイルオプション]** をクリックします。<br />4. **[デバッグ情報の生成]** ボックスの値を変更します。|

## <a name="example"></a>例

次の例では、デバッグ情報を出力ファイル `App.exe` に格納します。

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>関連項目

- [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
