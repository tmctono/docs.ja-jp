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
ms.openlocfilehash: c656f73748faf8be7124be65f3ed455f2d5fd07a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105186"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="7707c-102">StrongNameHashSize 関数</span><span class="sxs-lookup"><span data-stu-id="7707c-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="7707c-103">指定したハッシュ アルゴリズムを使用して、ハッシュに必須のバッファー サイズが取得されます。</span><span class="sxs-lookup"><span data-stu-id="7707c-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="7707c-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="7707c-104">This function has been deprecated.</span></span> <span data-ttu-id="7707c-105">代わりに[ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="7707c-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7707c-106">構文</span><span class="sxs-lookup"><span data-stu-id="7707c-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7707c-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7707c-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="7707c-108">からバッファーサイズを計算するために使用されるハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="7707c-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="7707c-109">入出力返されたバッファーサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7707c-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7707c-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="7707c-110">Return Value</span></span>  
 <span data-ttu-id="7707c-111">正常に完了した場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="7707c-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7707c-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="7707c-112">Remarks</span></span>  
 <span data-ttu-id="7707c-113">`StrongNameHashSize` 関数が正常に完了しない場合は、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)関数を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="7707c-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7707c-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="7707c-114">Requirements</span></span>  
 <span data-ttu-id="7707c-115">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7707c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7707c-116">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="7707c-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7707c-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7707c-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7707c-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7707c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7707c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7707c-119">See also</span></span>

- [<span data-ttu-id="7707c-120">StrongNameHashSize メソッド</span><span class="sxs-lookup"><span data-stu-id="7707c-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="7707c-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7707c-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
