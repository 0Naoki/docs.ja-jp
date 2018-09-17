---
title: 読み取り/書き込みロック
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8be9b4eef30333fbbdc26915635d17157176d6fc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2018
ms.locfileid: "45640934"
---
# <a name="reader-writer-locks"></a>読み取り/書き込みロック
<xref:System.Threading.ReaderWriterLockSlim> クラスを使用すると、複数のスレッドが同時に 1 つのリソースを読み取ることができますが、リソースに書き込むためには、排他的なロックを待機する必要があります。  
  
 アプリケーションで、<xref:System.Threading.ReaderWriterLockSlim> を使用して、共有リソースにアクセスするスレッド間で協調的に同期させる場合があります。 ロックは <xref:System.Threading.ReaderWriterLockSlim> 自体によって制御されます。  
  
 他のスレッド同期機構と同様に、<xref:System.Threading.ReaderWriterLockSlim> によって提供されるロックを回避するスレッドがないようにすることが必要です。 1 つの方法として、共有リソースをカプセル化するクラスをデザインする方法があります。 このクラスは、プライベートな共有リソースにアクセスするメンバーを提供します。このメンバーは、プライベートな <xref:System.Threading.ReaderWriterLockSlim> を使用して同期を行います。 たとえば、<xref:System.Threading.ReaderWriterLockSlim> クラスのコード例を参照してください。 <xref:System.Threading.ReaderWriterLockSlim> は効率的に動作するように設計されているので、個々のオブジェクトの同期に使用できます。  
  
 読み取り操作と書き込み操作の時間を最小限にするように、アプリケーションの構造を設計してください。 書き込みロックは排他的なので、書き込み操作の時間が長いと、その分、スループットが低下します。 読み取り操作時間が長いと、ライターを待たせることになります。また、書き込みアクセスを待機しているスレッドが 1 つでもあると、読み取りアクセスを要求するスレッドもブロックされます。  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] には、<xref:System.Threading.ReaderWriterLockSlim> と <xref:System.Threading.ReaderWriterLock> という 2 つのリーダー/ライター ロックがあります。 すべての新規開発で、<xref:System.Threading.ReaderWriterLockSlim> を使用することをお勧めします。 <xref:System.Threading.ReaderWriterLockSlim> は <xref:System.Threading.ReaderWriterLock> と似ていますが、再帰の規則や、ロック状態のアップグレードおよびダウングレードの規則が簡素化されています。 <xref:System.Threading.ReaderWriterLockSlim> は、デッドロックの可能性を大幅に回避します。 さらに、<xref:System.Threading.ReaderWriterLockSlim> のパフォーマンスは <xref:System.Threading.ReaderWriterLock> と比較して格段に優れています。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Threading.ReaderWriterLockSlim>  
- <xref:System.Threading.ReaderWriterLock>  
- [スレッド化](../../../docs/standard/threading/index.md)  
- [スレッド処理オブジェクトと機能](../../../docs/standard/threading/threading-objects-and-features.md)
