---
title: シリアル化バインダーの使用
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: bfce2a14c8757250c520919c8ff2a4d7048a9d5c
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138655"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="b5a80-102">シリアル化バインダーの使用</span><span class="sxs-lookup"><span data-stu-id="b5a80-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="b5a80-103">このサンプルでは、<xref:System.Runtime.Serialization.SerializationBinder> を使用して、ジェネリック型のバージョンをシリアル化する際に変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b5a80-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b5a80-104">使用例</span><span class="sxs-lookup"><span data-stu-id="b5a80-104">Demonstrates</span></span>  
 <span data-ttu-id="b5a80-105"><xref:System.Runtime.Serialization.SerializationBinder>、 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="b5a80-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b5a80-106">ディスカッション</span><span class="sxs-lookup"><span data-stu-id="b5a80-106">Discussion</span></span>  
 <span data-ttu-id="b5a80-107">このサンプルでは、異なるバージョンの .NET Framework を対象とする2つのエンティティが、バイナリフォーマッタとシリアル化バインダーを使用して通信できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b5a80-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="b5a80-108">このサンプルは、.NET リモート処理を使用して開発されました。</span><span class="sxs-lookup"><span data-stu-id="b5a80-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="b5a80-109">これは、.NET Framework 4 を対象とするサーバーで構成されます。このサーバーは、ジェネリック型のコントラクトと2つの異なるクライアント (1 つは 2.0 .NET Framework、もう1つは .NET Framework 4) を実装します。</span><span class="sxs-lookup"><span data-stu-id="b5a80-109">It consists of a server targeting .NET Framework 4, which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting .NET Framework 4.</span></span>  
  
 <span data-ttu-id="b5a80-110">このサーバーは、シリアル化の際に型のバージョンを相応に変更できるようにするために、<xref:System.Runtime.Serialization.SerializationBinder> をバイナリ フォーマッタにアタッチします。これにより、両方のクライアントで、これらの型を適切に逆シリアル化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b5a80-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b5a80-111">サンプルを設定、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="b5a80-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="b5a80-112">クライアントを実行するには、ソリューション SBGenericsVTS を右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5a80-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="b5a80-113">**[共通プロパティ]** で、 **[スタートアッププロジェクト]** を選択し、 **[マルチスタートアッププロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5a80-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="b5a80-114">**[サーバー]** 、 **[Client20]** 、 **[Client40]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b5a80-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="b5a80-115">これら3つのプロジェクトに対して **[開始]** アクションを選択し、残りの設定を **[なし]** のままにします。</span><span class="sxs-lookup"><span data-stu-id="b5a80-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="b5a80-116">[ **OK]** をクリックし、F5 キーを押してサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b5a80-116">Click **OK** and then press F5 to run the sample.</span></span>
