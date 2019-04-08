---
title: StrongNameFreeBuffer 関数
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bfc6491a1d18c81a44a7d9c5084f744c9b76281
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072578"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="86434-102">StrongNameFreeBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="86434-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="86434-103">[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)、[StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)、または[StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md) などの厳密な名前の関数に対する前の呼び出しで割り当てられたメモリが解放されます。</span><span class="sxs-lookup"><span data-stu-id="86434-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="86434-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="86434-104">This function has been deprecated.</span></span> <span data-ttu-id="86434-105">使用して、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="86434-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86434-106">構文</span><span class="sxs-lookup"><span data-stu-id="86434-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86434-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="86434-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="86434-108">[in]解放するメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="86434-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86434-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="86434-109">Requirements</span></span>  
 <span data-ttu-id="86434-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="86434-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86434-111">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="86434-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="86434-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="86434-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="86434-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="86434-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86434-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="86434-114">See also</span></span>

- [<span data-ttu-id="86434-115">StrongNameFreeBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="86434-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="86434-116">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="86434-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
