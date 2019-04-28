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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf9e3d2df8f507e118b393007c3958358a830cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763725"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="1e25b-102">ICLRStrongName2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e25b-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="1e25b-103">Sha-2 (sha-256、sha-384、および sha-512) のハッシュ アルゴリズムをセキュリティで保護グループを使用する厳密な名前を作成する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e25b-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e25b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e25b-104">Methods</span></span>  
  
|<span data-ttu-id="1e25b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e25b-105">Method</span></span>|<span data-ttu-id="1e25b-106">説明</span><span class="sxs-lookup"><span data-stu-id="1e25b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e25b-107">StrongNameGetPublicKeyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="1e25b-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="1e25b-108">公開/秘密キーのペアから公開キーを取得し、ハッシュ アルゴリズムおよび署名アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e25b-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="1e25b-109">StrongNameSignatureVerificationEx2 メソッド</span><span class="sxs-lookup"><span data-stu-id="1e25b-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="1e25b-110">厳密な名前付きのアセンブリの署名を検証し、ECMA キーから実際のキーへのマッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e25b-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e25b-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e25b-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e25b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="1e25b-112">Requirements</span></span>  
 <span data-ttu-id="1e25b-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e25b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e25b-114">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1e25b-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1e25b-115">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="1e25b-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e25b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e25b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
