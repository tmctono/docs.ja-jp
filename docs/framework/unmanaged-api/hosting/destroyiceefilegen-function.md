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
ms.openlocfilehash: ab4560774edce49341c86dd9446e38701db7fa62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769824"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="39f25-102">DestroyICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="39f25-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="39f25-103">破棄、 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="39f25-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="39f25-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="39f25-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f25-105">構文</span><span class="sxs-lookup"><span data-stu-id="39f25-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39f25-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39f25-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="39f25-107">[in]`ICeeFileGen`オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="39f25-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39f25-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="39f25-108">Return Value</span></span>  
 <span data-ttu-id="39f25-109">このメソッドは、標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="39f25-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39f25-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="39f25-110">Remarks</span></span>  
 <span data-ttu-id="39f25-111">`DestroyICeeFileGen` 破棄、`ICeeFileGen`によって作成されたオブジェクト、 [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="39f25-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39f25-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="39f25-112">Requirements</span></span>  
 <span data-ttu-id="39f25-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f25-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39f25-114">**ヘッダー:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="39f25-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="39f25-115">**ライブラリ:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="39f25-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="39f25-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39f25-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f25-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="39f25-117">See also</span></span>

- [<span data-ttu-id="39f25-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="39f25-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
