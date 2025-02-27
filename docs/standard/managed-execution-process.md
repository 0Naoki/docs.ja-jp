---
title: マネージド実行プロセス
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- source code language
- code, managed execution process
- runtime, managed execution process
- compiling source code, managed execution process
- managed execution process
- common language runtime, managed execution process
ms.assetid: 476b03dc-2b12-49a7-b067-41caeaa2f533
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d11567b3a5abca6e81ff0358295aa8516ef6443f
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969028"
---
# <a name="managed-execution-process"></a>マネージド実行プロセス
<a name="introduction"></a> マネージド実行プロセスで実行される主な手順を次に示します。詳細については、後で説明します。  
  
1. [コンパイラを選択します](#choosing_a_compiler)。  
  
     共通言語ランタイムが提供する機能を利用するためには、共通言語ランタイムに対応した言語コンパイラを使用する必要があります。  
  
2. [コードを MSIL にコンパイルします](#compiling_to_msil)。  
  
     コンパイルを実行するとソース コードが Microsoft Intermediate Language (MSIL) に変換され、必要なメタデータが生成されます。  
  
3. [MSIL からネイティブ コードにコンパイルします](#compiling_msil_to_native_code)。  
  
     実行時に、ジャスト イン タイム (JIT) コンパイラによって MSIL がネイティブ コードに変換されます。 このコンパイルの実行時に、コードは検証プロセスで確認される必要があります。この検証プロセスでは、MSIL とメタデータが調べられ、コードがタイプ セーフかどうかが確認されます。  
  
4. [コードを実行します](#running_code)。  
  
     共通言語ランタイムは、実行を可能にするインフラストラクチャと実行時に使用できるサービスを提供します。  
  
<a name="choosing_a_compiler"></a>   
## <a name="choosing-a-compiler"></a>コンパイラを選択します  
 共通言語ランタイム (CLR: Common Language Runtime) によって提供される機能を活用するには、Visual Basic、C#、Visual C++、F# などのランタイムに対応した言語コンパイラか、Eiffel、Perl、COBOL などのサードパーティのコンパイラを使用する必要があります。  
  
 共通言語ランタイムは多言語実行環境であるため、さまざまなデータ型と言語機能をサポートしています。 使用する言語コンパイラによって、利用できる共通言語ランタイムの機能が決まり、その機能を使用してコードをデザインすることになります。 記述するコードの構文を決定するのは、共通言語ランタイムではなく、使用するコンパイラです。 作成したコンポーネントを他の言語で記述されたコンポーネントでも完全に使用できるようにするためには、そのコンポーネントからエクスポートされた型が、 [言語への非依存性、および言語非依存コンポーネント](../../docs/standard/language-independence-and-language-independent-components.md) (CLS) に規定されている言語機能だけを公開するようにする必要があります。 <xref:System.CLSCompliantAttribute> 属性を使用することにより、コードを確実に CLS に準拠させることができます。 詳細については、「 [言語への非依存性、および言語非依存コンポーネント](../../docs/standard/language-independence-and-language-independent-components.md)」を参照してください。  
  
 [ページのトップへ](#introduction)  
  
<a name="compiling_to_msil"></a>   
## <a name="compiling-to-msil"></a>MSIL へのコンパイル  
 マネージド コードへのコンパイル時に、コンパイラはソース コードを MSIL (Microsoft Intermediate Language) に変換します。MSIL は CPU に依存しない一連の命令で、効率的にネイティブ コードに変換できます。 MSIL には、オブジェクトに対する読み込み、格納、初期化、および呼び出し用の命令の他に、算術演算と論理演算、制御フロー、DMA (Direct Memory Access)、例外処理、およびその他の操作のための命令も含まれています。 コードを実行する前に、MSIL を CPU 固有のコードに変換する必要があります。通常、この変換は [Just-In-Time (JIT) コンパイラ](#compiling_msil_to_native_code)によって行われます。 共通言語ランタイムはサポートするコンピューター アーキテクチャごとに JIT コンパイラを提供しているため、同じ MSIL セットを JIT コンパイルして、サポートされているすべてのアーキテクチャで実行できます。  
  
 コンパイラは、MSIL を生成するときにメタデータも生成します。 メタデータには、コード内の型について、それぞれの型の定義、型のメンバーのシグネチャ、コードが参照するメンバー、共通言語ランタイムが実行時に使用するその他のデータなどが記述されています。 MSIL とメタデータは、実行可能ファイルのファイル形式として使用されてきた従来の Microsoft PE と COFF (Common Object File Format) に基づき、それらを拡張した移植可能な実行可能 (PE: Portable Executable) ファイルに格納されます。 MSIL、ネイティブ コード、およびメタデータを保存できるこのファイル形式を使用すると、オペレーティング システムが共通言語ランタイムのイメージを認識できるようになります。 MSIL と共にメタデータがこのファイルに格納されるため、コードは自己記述型になります。つまり、タイプ ライブラリまたはインターフェイス定義言語 (IDL: Interface Definition Language) は必要ありません。 共通言語ランタイムは、実行時にこのファイルから必要に応じてメタデータを検出および抽出します。  
  
 [ページのトップへ](#introduction)  
  
<a name="compiling_msil_to_native_code"></a>   
## <a name="compiling-msil-to-native-code"></a>MSIL からネイティブ コードにコンパイルします  
 Microsoft Intermediate Language (MSIL) は、実行する前に、共通言語ランタイムに対して、対象コンピューターのアーキテクチャ用のネイティブ コードにコンパイルしておく必要があります。 .NET Framework には、この変換を実行する 2 つの方法が用意されています。  
  
- .NET Framework の Just-In-Time (JIT) コンパイラ  
  
- .NET Framework の [Ngen.exe (ネイティブ イメージ ジェネレーター)](../../docs/framework/tools/ngen-exe-native-image-generator.md)。  
  
### <a name="compilation-by-the-jit-compiler"></a>JIT コンパイラによるコンパイル  
 JIT コンパイルは、アプリケーション実行時に、アセンブリの内容が読み込まれて実行される際に、オン デマンドで MSIL をネイティブ コードに変換します。 共通言語ランタイムには、サポートされる CPU アーキテクチャごとに JIT コンパイラが用意されているため、開発者は MSIL アセンブリのセットを作成し、それを JIT でコンパイルして、異なるマシン アーキテクチャを持つさまざまなコンピューター上で実行できます。 ただし、マネージド コードがプラットフォーム固有のネイティブ API またはプラットフォーム固有のクラス ライブラリを呼び出す場合、そのコードはそのオペレーティング システムでしか実行されません。  
  
 JIT コンパイルは、実行時に呼び出されることがないコードがある可能性を考慮しています。 つまり、PE ファイル内にあるすべての MSIL をネイディブ コードに変換するために時間とメモリを費やす代わりに、実行時に必要とされる MSIL を変換し、結果として生成されるネイティブ コードをメモリに保存することで、そのプロセスのコンテキスト内の後続の呼び出しがこれを利用できるようにします。 型が読み込まれて初期化されるとき、ローダーはスタブを作成し、その型の各メソッドにそれを結び付けます。 メソッドが初めて呼び出されるとき、スタブは JIT コンパイラに制御を渡します。JIT コンパイラはそのメソッド用の MSIL をネイティブ コードに変換して、生成されたネイティブ コードを直接指すようスタブを変更します。 このため、JIT でコンパイルされたメソッドに対する後続の呼び出しでは、ネイティブ コードが直接実行されます。  
  
### <a name="install-time-code-generation-using-ngenexe"></a>NGen.exe を使用したインストール時のコード生成  
 JIT コンパイラは、アセンブリの MSIL を、そのアセンブリで定義されている個々のメソッドが呼び出されるときにネイティブ コードに変換するため、実行時のパフォーマンスが低下します。 ほとんどの場合、このパフォーマンスの低下は許容範囲内です。 より重要な点として、JIT コンパイラが生成したコードは、コンパイルを起動したプロセスにバインドされます。 複数のプロセスの間でこれを共有することはできません。 生成されたコードを、1 つのアプリケーションの複数の呼び出しの間で、または 1 つのアセンブリ セットを共有する複数のプロセスの間で共有できるようにするために、共通言語ランタイムは事前コンパイル モードをサポートします。 この Ahead Of Time コンパイル モードでは、[Ngen.exe (ネイティブ イメージ ジェネレーター)](../../docs/framework/tools/ngen-exe-native-image-generator.md) を使用して、JIT コンパイラと同様に MSIL アセンブリをネイティブ コードに変換します。 ただし、Ngen.exe の動作は、以下の 3 つの点で JIT コンパイラの動作と異なります。  
  
- MSIL からネイティブ コードへの変換を、アプリケーション実行中ではなく、実行前に行います。  
  
- メソッドを 1 つずつコンパイルするのではなく、アセンブリ全体を一度にコンパイルします。  
  
- 生成したコードを、ディスク上のファイルとしてネイティブ イメージ キャッシュに保持します。  
  
### <a name="code-verification"></a>コードの検証  
 コード検証の省略を許可するセキュリティ ポリシーを管理者が設定していない限り、MSIL からネイティブ コードへのコンパイル時に、MSIL コードは検証プロセスを通過する必要があります。 この検証プロセスでは、コードがタイプ セーフかどうかを確認するために、MSIL とメタデータが調べられます。タイプ セーフなコードとは、アクセス権限を与えられているメモリ位置だけにアクセスするコードを意味します。 タイプ セーフは、オブジェクトを相互に分離するため、不注意や悪意による破損からオブジェクトを保護するために役立ちます。 また、コードに対するセキュリティ制限が強制適用されることも保証されます。  
  
 共通言語ランタイムは、検証可能なタイプ セーフ コードが次の条件を満たすことを前提としています。  
  
- 型への参照には参照される型との間に完全な互換性がある。  
  
- 適切に定義された操作だけがオブジェクトに対して呼び出される。  
  
- ID が正しい。  
  
 検証プロセスでは、MSIL コードが調べられ、適切に定義された型だけを使用してメモリ位置にアクセスしたりメソッドを呼び出したりするかどうかが確認されます。 たとえば、オブジェクトのフィールドにアクセスするときにメモリ位置をオーバーランできるようなコードは許可されません。 また、不正な MSIL があるとタイプ セーフ規則に違反する可能性があるため、MSIL が正しく生成されているかどうかも調べられます。 検証プロセスは適切に定義されたタイプ セーフ コードのセットを許可します。許可されるコードはタイプ セーフなコードだけです。 ただし、タイプ セーフなコードの中にも、検証プロセスの制約事項のために検証を通過しないコードがあります。また、言語によっては、デザイン上、検証可能なタイプ セーフ コードが生成されない場合もあります。 セキュリティ ポリシーがタイプ セーフなコードを必要とするにもかかわらず、コードが検証を通過しない場合には、そのコードの実行時に例外がスローされます。  
  
 [ページのトップへ](#introduction)  
  
<a name="running_code"></a>   
## <a name="running-code"></a>コードを実行します  
 共通言語ランタイムは、マネージド実行を可能にするインフラストラクチャと実行時に使用できるサービスを提供します。 メソッドは、実行する前にプロセッサ固有のコードにコンパイルされている必要があります。 対応する MSIL が生成されているメソッドは、初めて呼び出されたときに JIT コンパイルされてから実行されます。 次にこのメソッドが実行されるときには、JIT コンパイル済みの既存のネイティブ コードが実行されます。 JIT コンパイルからコード実行までのプロセスは、実行が完了するまで繰り返されます。  
  
 実行時に、マネージド コードは、ガベージ コレクション、セキュリティ、アンマネージド コードとの相互運用性、言語間デバッグ サポート、強化された配置とバージョン管理のサポートなどのさまざまなサービスを利用できます。  
  
 Microsoft [!INCLUDE[winxp](../../includes/winxp-md.md)] および [!INCLUDE[windowsver](../../includes/windowsver-md.md)]では、オペレーティング システム ローダーが COFF ヘッダー内のビットを調べることにより、マネージド モジュールをチェックします。 設定されたビットはマネージド モジュールを意味します。 ローダーがマネージド モジュールを検出すると、mscoree.dll が読み込まれます。マネージド モジュール イメージが読み込まれるときとアンロードされるときには、 `_CorValidateImage` および `_CorImageUnloading` がローダーに通知します。 `_CorValidateImage` は、次のアクションを実行します。  
  
1. コードが有効なマネージド コードであることを確認します。  
  
2. イメージのエントリ ポイントをランタイムのエントリ ポイントに変更します。  
  
 64 ビット Windows では、 `_CorValidateImage` は、メモリ内のイメージを PE32 から PE32+ 形式に変換することによって変更します。  
  
 [ページのトップへ](#introduction)  
  
## <a name="see-also"></a>関連項目

- [概要](../../docs/framework/get-started/overview.md)
- [言語への非依存性、および言語非依存コンポーネント](../../docs/standard/language-independence-and-language-independent-components.md)
- [メタデータと自己言及的なコンポーネント](../../docs/standard/metadata-and-self-describing-components.md)
- [Ilasm.exe (IL アセンブラー)](../../docs/framework/tools/ilasm-exe-il-assembler.md)
- [セキュリティ](../../docs/standard/security/index.md)
- [アンマネージ コードとの相互運用](../../docs/framework/interop/index.md)
- [配置](../../docs/framework/deployment/net-framework-applications.md)
- [.NET のアセンブリ](assembly/index.md)
- [アプリケーション ドメイン](../../docs/framework/app-domains/application-domains.md)
