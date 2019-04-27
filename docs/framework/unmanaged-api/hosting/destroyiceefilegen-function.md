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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906361"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="a18ba-102">DestroyICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="a18ba-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="a18ba-103">破棄、 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a18ba-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="a18ba-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="a18ba-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a18ba-105">構文</span><span class="sxs-lookup"><span data-stu-id="a18ba-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a18ba-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a18ba-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="a18ba-107">[in]`ICeeFileGen`オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="a18ba-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a18ba-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a18ba-108">Return Value</span></span>  
 <span data-ttu-id="a18ba-109">このメソッドは、標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="a18ba-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a18ba-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a18ba-110">Remarks</span></span>  
 <span data-ttu-id="a18ba-111">`DestroyICeeFileGen` 破棄、`ICeeFileGen`によって作成されたオブジェクト、 [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="a18ba-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a18ba-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a18ba-112">Requirements</span></span>  
 <span data-ttu-id="a18ba-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a18ba-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a18ba-114">**ヘッダー:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="a18ba-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="a18ba-115">**ライブラリ:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="a18ba-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="a18ba-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a18ba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a18ba-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a18ba-117">See also</span></span>

- [<span data-ttu-id="a18ba-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="a18ba-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
