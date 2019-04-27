---
title: 暗号スキームの作成
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ef3741ef5cec720c2fb285c9aa60d610acc0be9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909390"
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="bf17d-102">暗号スキームの作成</span><span class="sxs-lookup"><span data-stu-id="bf17d-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="bf17d-103">.NET Framework の暗号化コンポーネントを組み合わせて、データの暗号化と復号化を行うさまざまなスキームを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bf17d-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="bf17d-104">データの暗号化と復号化の単純な暗号スキームでは、次の手順を指定することがあります。</span><span class="sxs-lookup"><span data-stu-id="bf17d-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1. <span data-ttu-id="bf17d-105">暗号化側と復号化側は、公開キーと秘密キーのペアを生成する。</span><span class="sxs-lookup"><span data-stu-id="bf17d-105">Each party generates a public/private key pair.</span></span>  
  
2. <span data-ttu-id="bf17d-106">暗号化側と復号化側は、公開キーを交換する。</span><span class="sxs-lookup"><span data-stu-id="bf17d-106">The parties exchange their public keys.</span></span>  
  
3. <span data-ttu-id="bf17d-107">暗号化側と復号化側は、たとえば TripleDES 暗号化の秘密キーを生成する。続いて、相手側の公開キーを使用して新規作成されたキーを暗号化する。</span><span class="sxs-lookup"><span data-stu-id="bf17d-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4. <span data-ttu-id="bf17d-108">暗号化側と復号化側は、相手側にデータを送信し、特定の順序で相手側の秘密キーを自分の秘密キーと組み合わせて、新しい秘密キーを作成する。</span><span class="sxs-lookup"><span data-stu-id="bf17d-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5. <span data-ttu-id="bf17d-109">暗号化側と復号化側は、対称暗号化を使って会話を開始する。</span><span class="sxs-lookup"><span data-stu-id="bf17d-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="bf17d-110">暗号スキームの作成は簡単なタスクではありません。</span><span class="sxs-lookup"><span data-stu-id="bf17d-110">Creating a cryptographic scheme is not a trivial task.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bf17d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf17d-111">See also</span></span>

- [<span data-ttu-id="bf17d-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="bf17d-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
