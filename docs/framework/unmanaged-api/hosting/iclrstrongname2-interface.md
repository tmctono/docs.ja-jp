---
title: ICLRStrongName2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: bc871c29f53a9ea4451a0fc1c747939724b0da87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092241"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="32c76-102">ICLRStrongName2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32c76-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="32c76-103">セキュリティで保護されたハッシュアルゴリズム (SHA-256、SHA-384、および SHA-512) の SHA-1 グループを使用して、厳密な名前を作成する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="32c76-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="32c76-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="32c76-104">Methods</span></span>  
  
|<span data-ttu-id="32c76-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="32c76-105">Method</span></span>|<span data-ttu-id="32c76-106">説明</span><span class="sxs-lookup"><span data-stu-id="32c76-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="32c76-107">StrongNameGetPublicKeyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="32c76-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="32c76-108">公開キーと秘密キーのペアから公開キーを取得し、ハッシュアルゴリズムと署名アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="32c76-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="32c76-109">StrongNameSignatureVerificationEx2 メソッド</span><span class="sxs-lookup"><span data-stu-id="32c76-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="32c76-110">厳密に名前が付けられたアセンブリの署名を検証し、ECMA キーから実際のキーへのマッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="32c76-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32c76-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="32c76-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32c76-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="32c76-112">Requirements</span></span>  
 <span data-ttu-id="32c76-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32c76-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32c76-114">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="32c76-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="32c76-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="32c76-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32c76-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32c76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
