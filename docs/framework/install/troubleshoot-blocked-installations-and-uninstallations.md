---
title: .NET Framework のインストールおよびアンインストールのブロックのトラブルシューティング
ms.date: 04/18/2019
ms.custom: updateeachrelease
helpviewer_keywords:
- .NET Framework, troubleshooting blocked installations
- blocked .NET Framework installations, troubleshooting
ms.assetid: c3fdfbc1-ed99-4202-a2b0-8c4f1646385d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e932399b1d199fc69d4a541e7ee2298bc5526e2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051916"
---
# <a name="troubleshoot-blocked-net-framework-installations-and-uninstallations"></a>.NET Framework のインストールおよびアンインストールのブロックのトラブルシューティング

.NET Framework 4.5 以降のバージョンの [Web またはオフラインのインストーラー](guide-for-developers.md)を実行すると、.NET Framework のインストールを妨げたりブロックしたりする問題が発生することがあります。 次の表に、インストールをブロックすることが考えられる問題と、トラブルシューティング情報へのリンクを示します。

Windows 8 以降では、.NET Framework はオペレーティング システム コンポーネントとなっているため、個別にアンインストールすることはできません。 .NET Framework の更新プログラムは、コントロール パネルの **[プログラムと機能]** アプリの **[インストールされた更新プログラム]** タブに表示されます。 .NET Framework がプレインストールされていないオペレーティング システムでは、.NET Framework は、コントロール パネルの **[プログラムと機能]** アプリの **[プログラムのアンインストールまたは変更]** タブ (または **[プログラムの追加と削除]** タブ) に表示されます。 .NET Framework がプレインストールされている Windows のバージョンについては、[システム要件](../get-started/system-requirements.md)に関するページを参照してください。

> [!IMPORTANT]
> .NET framework の 4.x バージョンはインプレース更新であるため、最新バージョンが既にインストールされているシステムに .NET Framework 4.x の以前のバージョンをインストールすることはできません。 たとえば、Windows 10 Fall Creators Update がインストール済みのシステムでは、.NET Framework 4.7.1 がオペレーティング システムと共にプレインストールされているため、.NET Framework 4.6.2 をインストールすることはできません。

システムにインストールされている .NET Framework のバージョンを確認してください。 「[方法:インストールされている .NET Framework バージョンを確認する](../migration-guide/how-to-determine-which-versions-are-installed.md)」を参照してください。

この表では、4.5.x は .NET Framework 4.5 とそのポイント リリースである 4.5.1 と 4.5.2 を指し、4.6.x は .NET Framework 4.6 とそのポイント リリースである 4.6.1 と 4.6.2 を指し、4.7.x は .NET Framework 4.7 とそのポイント リリースである 4.7.1 と 4.7.2 を指し、4.8 は .NET Framework 4.8 を指します。

|ブロッキング メッセージ|詳細情報または問題解決のための参照先|  
|----------------------|--------------------------------------------------|  
|Microsoft .NET Framework をアンインストールすると、一部のアプリケーションが機能しなくなる可能性があります。|一般に、コンピューターにインストールされている .NET Framework のバージョンはアンインストールしないでください。使用するアプリケーションが .NET Framework の特定のバージョンに依存している可能性があるからです。 詳しくは、*概要*ガイドの「[ユーザーにとっての .NET Framework](../get-started/index.md#ForUsers)」をご覧ください。|  
|このコンピューターには、.4.5.x/4.6.x/4.7.x (ENU) 以降のバージョンが既にインストールされています。|アクションは必要ありません。<br /><br /> システムにインストールされている .NET Framework のバージョンを確認する方法については、「[方法:インストールされている .NET Framework バージョンを確認する](../migration-guide/how-to-determine-which-versions-are-installed.md)」を参照してください。|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 (<*言語*>) には、.NET Framework 4.5.x/4.6.x/4.7.x/4.8 が必要です。 ダウンロード センターから .NET Framework 4.5.x/4.6.x/4.7.x/4.8 をインストールして、セットアップを再実行してください。|言語パックをインストールする前に、指定された .NET Framework リリースの英語バージョンをインストールする必要があります。 詳細については、インストール ガイドの「[言語パックのインストール](guide-for-developers.md#to-install-language-packs)」を参照してください。|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 をインストールできません。 このプログラムと互換性がないアプリケーションがコンピューター上に存在します。<br /><br /> または<br /><br /> このプログラムと互換性がないアプリケーションがコンピューター上に存在します。|このメッセージは、通常 .NET Framework のプレビューまたは RC バージョンがインストールされているために表示されます。 プレビューまたは RC バージョンをアンインストールし、セットアップを再実行します。|  
|このパッケージを使用して .NET Framework 4.5.x/4.6.x/4.7.x/4.8 をアンインストールすることはできません。 コンピューターから .NET Framework 4.5.x/4.6.x/4.7.x/4.8 をアンインストールするには、**コントロール パネル**で **[プログラムと機能]** 、 **[インストールされた更新プログラムを表示]** を選択し、[Microsoft Windows (KB2828152) の更新プログラム] を選択して、 **[アンインストール]** を選択します。|インストールしているパッケージによって、.NET Framework のプレビューまたは RC リリースはアンインストールされません。<br /><br /> コントロール パネルからプレビューまたは RC リリースをアンインストールします。|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 をアンインストールできません。 このプログラムに依存するアプリケーションがコンピューター上に存在します。|一般に、コンピューターから .NET Framework のバージョンをアンインストールしないでください。使用するアプリケーションが .NET Framework の特定のバージョンに依存している可能性があるからです。 詳しくは、*概要*ガイドの「[ユーザーにとっての .NET Framework](../get-started/index.md#ForUsers)」をご覧ください。|  
|再頒布可能な .NET Framework 4.5.x/4.6.x/4.7.x/4.8 は、このオペレーティング システムには適用されません。 Microsoft ダウンロード センターからご使用のオペレーティング システムに対応した .NET Framework 4.5.x/4.6.x/4.7.x/4.8 をダウンロードしてください。|サポートされていないプラットフォームに .NET Framework 4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1、4.7.2、4.8 をインストールしようとしている可能性があります。または、サポートされているすべてのオペレーティング システム用のコンポーネントが含まれていないインストール パッケージを選択しました。 オフライン インストーラー ([4.5.1 用](https://go.microsoft.com/fwlink/p/?LinkId=309493)、[4.5.2 用](https://go.microsoft.com/fwlink/p/?LinkId=397706)、[4.6 用](https://go.microsoft.com/fwlink/p/?LinkId=528233)、[4.6.1 用](https://go.microsoft.com/fwlink/p/?LinkId=671744)、[4.6.2 用](https://go.microsoft.com/fwlink/p/?LinkId=780604)、[4.7 用](https://go.microsoft.com/fwlink/p/?LinkId=825306)、[4.7.1 用](https://go.microsoft.com/fwlink/p/?LinkId=852090)、[4.7.2 用](https://go.microsoft.com/fwlink/p/?LinkId=863265)、[4.8 用](https://go.microsoft.com/fwlink/?linkid=2088631)) を使用してインストールを再実行します。 サポートされているオペレーティング システムの詳細については、[インストール ガイド](guide-for-developers.md)に関するページおよび[システム要件](../get-started/system-requirements.md)に関するページを参照してください。|  
|この製品をインストールする前に、KB\<*番号*> に対応する更新プログラムがインストールされている必要があります。|.NET Framework のインストールでは、.NET Framework をインストールする前に KB の更新プログラムをインストールする必要があります。 更新プログラムをインストールしてから、.NET Framework のインストールをもう一度開始します。<br /><br /> たとえば、Windows 8.1、Windows RT 8.1、Windows Server 2012 R2 に .NET Framework の最新バージョンをインストールするには、[KB2919355](https://support.microsoft.com/kb/2919355) に対応する更新プログラムをインストールする必要があります。|  
|現在、コンピューターでは Windows Server 2008 オペレーティング システムの Server Core インストールが実行されています。 .NET Framework 4.5.x には、新しいリリースのオペレーティング システムが必要です。 Windows Server 2008 R2 SP1 以上をインストールし、.NET Framework 4.5.x セットアップを再実行してください。|.NET Framework 4.5.1 と 4.5.2 は、Windows Server 2008 R2 SP1 以降の Server Core ロールでサポートされています。 [システム要件](../get-started/system-requirements.md)に関するページを参照してください。|  
|特権が不十分なため、このコンピューターのすべてのユーザーが使用できるようにセットアップを完了できません。 管理者としてログオンし、**セットアップ**を再度実行してください。|.NET Framework をインストールするには、そのコンピューターの管理者である必要があります。|  
|前のインストールを完了するためにコンピューターの再起動が必要であるため、セットアップを続行できません。 コンピューターを再起動し、セットアップを再度実行してください。|インストールを完了するために、再起動が必要な場合があります。 手順に従って、コンピューターを再起動し、セットアップを再実行します。<br /><br /> まれに、Windows で不足している更新プログラムが多数検出され、次の順番の更新プログラムをインストールするための再起動を行っている場合、システムを複数回再起動するように求められることがあります。|  
|.NET Framework Setup cannot be run in Program Compatibility Mode. (プログラム互換性モードで .NET Framework セットアップを実行できません。)|この記事で後述する「[プログラムの互換性問題](#compat)」セクションを参照してください。|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 は、コンポーネント ストアが破損しているためにインストールされませんでした。|詳細については、「[DISM またはシステム更新準備ツールを使用して Windows Update のエラーを解決する](https://support.microsoft.com/kb/947821)」を参照してください。|  
|Setup cannot run because the Windows Installer Service is not available on this computer. (このコンピューターには利用できる Windows インストーラー サービスがないため、セットアップは実行できません。)|Microsoft サポート オンラインの[プログラムをインストールまたは更新するときの Windows インストーラー サービス エラー](https://go.microsoft.com/fwlink/p/?LinkId=248684)に関するページを参照してください。|  
|Setup may not run properly because the Windows Update Service is not available on this computer. (このコンピューターには利用できる Windows Update サービスがありません。セットアップは正しく実行されない可能性があります。)|管理者によって、コンピューターが Microsoft Windows Update ではなく Windows Server Update Services (WSUS) を使用するように設定されています。 詳細については、[Windows 8 または Windows Server 2012 での NET Framework 3.5 をインストール時に表示されるエラー コード](https://support.microsoft.com/kb/2734782)に関するページのエラー コード 0x800F0906 のセクションを参照してください。<br /><br /> Microsoft サポート オンラインの[最新版の Windows Update エージェントを入手してコンピューターの更新プログラムを管理する方法](https://go.microsoft.com/fwlink/p/?LinkId=248437)に関するページも参照してください。|  
|Setup may not run properly because the Background Intelligent Transfer Service (BITS) is not available on this computer. (このコンピューターには利用できる Background Intelligent Transfer Service (BITS) がありません。セットアップは正しく実行されない可能性があります。)|Microsoft サポート オンラインの「[An update to prevent a Background Intelligent Transfer Service (BITS) crash on a Windows Vista-based computer](https://go.microsoft.com/fwlink/p/?LinkId=248680)」(Windows Vista ベースのコンピューターでのバックグラウンド インテリジェント転送サービス (BITS) のクラッシュを防止する更新プログラム) を参照してください。|  
|Windows Update にエラーが発生しエラー コード 0x80070643 または 0x643 が表示されたため、セットアップは正しく実行されない可能性があります。|Microsoft サポート オンラインの [.NET Framework 更新プログラムのインストール エラー"0x80070643" または "0x643"](https://support.microsoft.com/kb/976982) に関するページを参照してください。|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 は、既にこのオペレーティング システムにインストールされています。 .NET Framework 4.5.x/4.6.x/4.7.x/4.8 再頒布可能パッケージをインストールする必要はありません。|アクションなし。<br /><br /> システムにインストールされている .NET Framework のバージョンを確認する方法については、「[方法:インストールされている .NET Framework バージョンを確認する](../migration-guide/how-to-determine-which-versions-are-installed.md)」を参照してください。 サポートされるオペレーティング システムについては、[システム要件](../get-started/system-requirements.md)に関するページをご覧ください。|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 は、このオペレーティング システムではサポートされていません。|サポートされるオペレーティング システムについては、[システム要件](../get-started/system-requirements.md)に関するページをご覧ください。<br /><br /> Windows 7 での .NET Framework のインストールに失敗した場合、通常このメッセージは Windows 7 SP1 がインストールされていないことを示します。 Windows 7 システムでは、.NET Framework には Windows 7 SP1 が必要です。 Windows 7 を使用していて Service Pack 1 をインストールしていない場合、.NET Framework をインストールする前に、Service Pack 1 をインストールする必要があります。 Windows 7 SP1 のインストールの詳細については、[Windows 7 Service Pack 1 (SP1) のインストール方法の詳細](https://windows.microsoft.com/windows7/install-windows-7-service-pack-1)に関するページを参照してください。|  
|Your computer is currently running a Server Core installation of Windows Server 2008 operating system. (現在、コンピューターでは Windows Server 2008 オペレーティング システムの Server Core インストールが実行されています。) .NET Framework 4.5.x には、オペレーティング システムまたは Server Core 2008 R2 SP1 の完全なリリースが必要です。 Windows Server 2008 SP2、Windows Server 2008 R2 SP1、Server Core 2008 R2 SP1 のいずれかの完全バージョンをインストールして、.NET Framework 4.5.x セットアップを再度実行してください。|.NET Framework は、Windows Server 2008 R2 SP1 以降の Server Core ロールでサポートされています。 [システム要件](../get-started/system-requirements.md)に関するページを参照してください。|  
|.NET Framework 4.5.x は既にこのオペレーティング システムの一部として組み込まれていますが、現在は無効になっています ([!INCLUDE[winserver8](../../../includes/winserver8-md.md)] のみ)。|Windows Web サイトの [Windows の機能の有効化または無効化](https://go.microsoft.com/fwlink/p/?LinkId=248438)に関するページを参照してください。|  
|このセットアップ プログラムは x86 コンピューターのみを対象としています。 x64 コンピューターまたは IA64 コンピューターにはインストールできません。|[システム要件](../get-started/system-requirements.md)に関するページを参照してください。|  
|このセットアップ プログラムは x64 コンピューターまたは x86 コンピューターのみを対象としています。 IA64 コンピューターにはインストールできません。|[システム要件](../get-started/system-requirements.md)に関するページを参照してください。|  

<a name="compat"></a>
### <a name="program-compatibility-issues"></a>プログラムの互換性問題

.NET Framework 4.5 またはそのポイント リリースのインストールを Windows プログラム互換性モードで実行すると、1603 エラー コードで失敗するか、ブロックされます。 **プログラム互換性アシスタント**により、.NET Framework が正しくインストールされていない可能性が示され、推奨設定 (プログラム互換性モード) を使用して再インストールするよう求められます。 プログラム互換性モードは、以前の .NET Framework セットアップの実行が失敗するか取り消されたときにプログラム互換性アシスタントによって設定されている可能性もあります。

プログラム互換性モードで .NET Framework インストーラーを実行できません。 このブロッキング問題を解決するには、レジストリ エディターを使用し、システム全体での互換性モードの設定が無効になるようにする必要があります。

1. **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** を選択します。

1. **[ファイル名を指定して実行]** ダイアログ ボックスで、「regedit」と入力し、 **[OK]** をクリックします。

1. レジストリ エディターで、次のサブキーを参照します。

   - HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Compatibility Assistant\Persisted

   - HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers

1. [名前] 列で、インストールしているバージョンに応じて .NET Framework 4.5、4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1、または 4.7.2 のダウンロード名を検索し、これらのエントリを削除します。 ダウンロード名については、「[開発者向けの .NET Framework のインストール](guide-for-developers.md)」の記事を参照してください。

1. バージョン 4.5、4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1、または 4.7.2 の .NET Framework インストーラーを再実行します。

## <a name="see-also"></a>関連項目

- [開発者向けの .NET Framework のインストール](guide-for-developers.md)
- [方法: インストールされている .NET Framework バージョンを確認する](../migration-guide/how-to-determine-which-versions-are-installed.md)
- [バージョンおよび依存関係](../migration-guide/versions-and-dependencies.md)
