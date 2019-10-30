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
ms.openlocfilehash: 4eb878b61b72378bc6870af7f2cd09f0b6943b13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136499"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="05cad-102">DestroyICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="05cad-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="05cad-103">[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="05cad-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="05cad-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="05cad-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05cad-105">構文</span><span class="sxs-lookup"><span data-stu-id="05cad-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05cad-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="05cad-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="05cad-107">から破棄する `ICeeFileGen` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="05cad-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05cad-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="05cad-108">Return Value</span></span>  
 <span data-ttu-id="05cad-109">このメソッドは、標準の COM エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="05cad-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05cad-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="05cad-110">Remarks</span></span>  
 <span data-ttu-id="05cad-111">`DestroyICeeFileGen` は、 [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)関数によって作成された `ICeeFileGen` オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="05cad-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05cad-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="05cad-112">Requirements</span></span>  
 <span data-ttu-id="05cad-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05cad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05cad-114">**ヘッダー:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="05cad-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="05cad-115">**ライブラリ:** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="05cad-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="05cad-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05cad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05cad-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="05cad-117">See also</span></span>

- [<span data-ttu-id="05cad-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="05cad-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
