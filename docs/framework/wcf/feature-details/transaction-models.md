---
title: トランザクション モデル
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 2d3d0631c47506e7bd99d90ed49a1fdc76cc7a59
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556825"
---
# <a name="transaction-models"></a>トランザクション モデル
ここでは、トランザクション プログラミング モデルと、マイクロソフトが提供するインフラストラクチャ コンポーネントとの関係を説明します。  
  
 Windows Communication Foundation (WCF) でトランザクションを使用する場合は、異なるトランザクションモデルを選択するのではなく、統合された一貫性のあるモデルの異なる層で操作することを理解しておくことが重要です。  
  
 以下に、3 つの主要なトランザクション コンポーネントについて説明します。  
  
## <a name="windows-communication-foundation-transactions"></a>Windows Communication Foundation トランザクション  
 WCF でのトランザクションのサポートにより、トランザクションサービスを記述することができます。 さらに、ws-atomictransaction (WS-AT) プロトコルのサポートにより、アプリケーションは、WCF またはサードパーティのテクノロジを使用して構築された Web サービスにトランザクションをフローさせることができます。  
  
 WCF サービスまたはアプリケーションでは、WCF トランザクション機能によって属性と構成が提供され、インフラストラクチャがトランザクションを作成、フロー、および同期する方法とタイミングを宣言によって指定できます。  
  
## <a name="systemtransactions-transactions"></a>System.Transactions トランザクション  
 <xref:System.Transactions> 名前空間は、<xref:System.Transactions.Transaction> クラスに基づく明示的なプログラミング モデルだけでなく、インフラストラクチャがトランザクションを自動的に管理する、<xref:System.Transactions.TransactionScope> クラスを使用した暗黙的なプログラミング モデルも提供します。  
  
 これら2つのモデルを使用してトランザクションアプリケーションを作成する方法の詳細については、「 [トランザクションアプリケーションの](https://go.microsoft.com/fwlink/?LinkId=94947)作成」を参照してください。  
  
 WCF サービスまたはアプリケーションでは、は、 <xref:System.Transactions> クライアントアプリケーション内でトランザクションを作成するためのプログラミングモデルを提供し、必要に応じてサービス内でトランザクションを明示的に操作します。  
  
## <a name="msdtc-transactions"></a>MSDTC トランザクション  
 Microsoft 分散トランザクション コーディネーター (MSDTC) は、分散トランザクションをサポートするトランザクション マネージャーです。  
  
 詳細については、「 [DTC プログラマーズリファレンス](/previous-versions/windows/desktop/ms686108(v=vs.85))」を参照してください。  
  
 WCF サービスまたはアプリケーションでは、MSDTC によって、クライアントまたはサービス内で作成されたトランザクションを調整するためのインフラストラクチャが提供されます。
