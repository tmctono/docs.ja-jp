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
ms.openlocfilehash: daf674c0340998c0fd518e0f1af721bbe9ff653c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490472"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="fe65b-102">DestroyICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="fe65b-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="fe65b-103">破棄、 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fe65b-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="fe65b-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="fe65b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe65b-105">構文</span><span class="sxs-lookup"><span data-stu-id="fe65b-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe65b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe65b-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="fe65b-107">[in]`ICeeFileGen`オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="fe65b-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe65b-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="fe65b-108">Return Value</span></span>  
 <span data-ttu-id="fe65b-109">このメソッドは、標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="fe65b-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe65b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe65b-110">Remarks</span></span>  
 <span data-ttu-id="fe65b-111">`DestroyICeeFileGen` 破棄、`ICeeFileGen`によって作成されたオブジェクト、 [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="fe65b-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe65b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe65b-112">Requirements</span></span>  
 <span data-ttu-id="fe65b-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe65b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe65b-114">**ヘッダー:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="fe65b-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="fe65b-115">**ライブラリ:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="fe65b-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="fe65b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe65b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe65b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe65b-117">See also</span></span>

- [<span data-ttu-id="fe65b-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="fe65b-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
