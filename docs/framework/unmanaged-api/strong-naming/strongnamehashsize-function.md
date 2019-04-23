---
title: StrongNameHashSize 関数
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7e807b502e0905f9ae785203289447c71d25e04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072146"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="cbdea-102">StrongNameHashSize 関数</span><span class="sxs-lookup"><span data-stu-id="cbdea-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="cbdea-103">指定したハッシュ アルゴリズムを使用して、ハッシュに必須のバッファー サイズが取得されます。</span><span class="sxs-lookup"><span data-stu-id="cbdea-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="cbdea-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="cbdea-104">This function has been deprecated.</span></span> <span data-ttu-id="cbdea-105">使用して、 [iclrstrongname::strongnamehashsize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="cbdea-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbdea-106">構文</span><span class="sxs-lookup"><span data-stu-id="cbdea-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbdea-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbdea-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="cbdea-108">[in]バッファー サイズを計算するために使用するハッシュ アルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="cbdea-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="cbdea-109">[out]返されたバッファー サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="cbdea-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbdea-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="cbdea-110">Return Value</span></span>  
 <span data-ttu-id="cbdea-111">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="cbdea-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbdea-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbdea-112">Remarks</span></span>  
 <span data-ttu-id="cbdea-113">場合、`StrongNameHashSize`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="cbdea-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbdea-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="cbdea-114">Requirements</span></span>  
 <span data-ttu-id="cbdea-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbdea-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbdea-116">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cbdea-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cbdea-117">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cbdea-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbdea-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbdea-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbdea-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbdea-119">See also</span></span>

- [<span data-ttu-id="cbdea-120">StrongNameHashSize メソッド</span><span class="sxs-lookup"><span data-stu-id="cbdea-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="cbdea-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbdea-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
