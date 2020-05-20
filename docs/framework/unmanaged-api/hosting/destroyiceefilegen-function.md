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
ms.openlocfilehash: ff7e7b299d185b8db263d2076c1e075b87b487fc
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616399"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="f7a0d-102">DestroyICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="f7a0d-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="f7a0d-103">[ICeeFileGen](iceefilegen-class.md)オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="f7a0d-103">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="f7a0d-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="f7a0d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7a0d-105">構文</span><span class="sxs-lookup"><span data-stu-id="f7a0d-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7a0d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7a0d-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="f7a0d-107">から`ICeeFileGen`破棄するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f7a0d-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7a0d-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f7a0d-108">Return Value</span></span>  
 <span data-ttu-id="f7a0d-109">このメソッドは、標準の COM エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="f7a0d-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7a0d-110">解説</span><span class="sxs-lookup"><span data-stu-id="f7a0d-110">Remarks</span></span>  
 <span data-ttu-id="f7a0d-111">`DestroyICeeFileGen``ICeeFileGen` [CreateICeeFileGen](createiceefilegen-function.md)関数によって作成されたオブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="f7a0d-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7a0d-112">要件</span><span class="sxs-lookup"><span data-stu-id="f7a0d-112">Requirements</span></span>  
 <span data-ttu-id="f7a0d-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7a0d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7a0d-114">**ヘッダー:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="f7a0d-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="f7a0d-115">**ライブラリ:** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="f7a0d-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="f7a0d-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7a0d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a0d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7a0d-117">See also</span></span>

- [<span data-ttu-id="f7a0d-118">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="f7a0d-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
