---
title: '方法: ネットワークの可用性とアドレスの変更を検出する'
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
ms.openlocfilehash: 9e265a97d339da59bb9d0af6ab6757e16af00e06
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894962"
---
# <a name="how-to-detect-network-availability-and-address-changes"></a><span data-ttu-id="c1a9b-102">方法: ネットワークの可用性とアドレスの変更を検出する</span><span class="sxs-lookup"><span data-stu-id="c1a9b-102">How to: Detect Network Availability and Address Changes</span></span>
<span data-ttu-id="c1a9b-103">このサンプルでは、インターフェイスのネットワーク アドレスの変更を検出する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c1a9b-103">This sample shows how to detect changes in the network address of an interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1a9b-104">例</span><span class="sxs-lookup"><span data-stu-id="c1a9b-104">Example</span></span>  
  
```csharp
using System;  
using System.Net;  
using System.Net.NetworkInformation;  
  
namespace Examples.Net.AddressChanges  
{  
    public class NetworkingExample  
    {  
        public static void Main()  
        {  
            NetworkChange.NetworkAddressChanged += new
             NetworkAddressChangedEventHandler(AddressChangedCallback);  
            Console.WriteLine("Listening for address changes. Press any key to exit.");  
            Console.ReadLine();  
        }  
        static void AddressChangedCallback(object sender, EventArgs e)  
        {  
  
            NetworkInterface[] adapters = NetworkInterface.GetAllNetworkInterfaces();  
            foreach(NetworkInterface n in adapters)  
            {  
                Console.WriteLine("   {0} is {1}", n.Name, n.OperationalStatus);  
            }  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c1a9b-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c1a9b-105">Compiling the Code</span></span>  
 <span data-ttu-id="c1a9b-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c1a9b-106">This example requires:</span></span>  
  
- <span data-ttu-id="c1a9b-107">**System.Net** 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="c1a9b-107">References to the **System.Net** namespace.</span></span>
