---
title: DestroyICeeFileGen 関数
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37ff40e1c009b8e1e0509a4a3333d5a2a70bbfd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159888"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="6633a-102">DestroyICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="6633a-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="6633a-103">破棄、 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6633a-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="6633a-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="6633a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6633a-105">構文</span><span class="sxs-lookup"><span data-stu-id="6633a-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6633a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6633a-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="6633a-107">[in]`ICeeFileGen`オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="6633a-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6633a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="6633a-108">Return Value</span></span>  
 <span data-ttu-id="6633a-109">このメソッドは、標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="6633a-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6633a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6633a-110">Remarks</span></span>  
 `DestroyICeeFileGen` <span data-ttu-id="6633a-111">破棄、`ICeeFileGen`によって作成されたオブジェクト、 [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="6633a-111">destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6633a-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="6633a-112">Requirements</span></span>  
 <span data-ttu-id="6633a-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6633a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6633a-114">**ヘッダー:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="6633a-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="6633a-115">**ライブラリ:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="6633a-115">**Library:** MSCorPE.dll</span></span>  
  
 **<span data-ttu-id="6633a-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6633a-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6633a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6633a-117">See also</span></span>

- [<span data-ttu-id="6633a-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="6633a-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
