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
ms.openlocfilehash: 53384a5aa7f8d11f868057f892f7b60aac2e9f02
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799034"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="30e66-102">StrongNameHashSize 関数</span><span class="sxs-lookup"><span data-stu-id="30e66-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="30e66-103">指定したハッシュ アルゴリズムを使用して、ハッシュに必須のバッファー サイズが取得されます。</span><span class="sxs-lookup"><span data-stu-id="30e66-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="30e66-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="30e66-104">This function has been deprecated.</span></span> <span data-ttu-id="30e66-105">代わりに[ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="30e66-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e66-106">構文</span><span class="sxs-lookup"><span data-stu-id="30e66-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30e66-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30e66-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="30e66-108">からバッファーサイズを計算するために使用されるハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="30e66-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="30e66-109">入出力返されたバッファーサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="30e66-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30e66-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="30e66-110">Return Value</span></span>  
 <span data-ttu-id="30e66-111">`true`正常に完了した場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="30e66-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30e66-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="30e66-112">Remarks</span></span>  
 <span data-ttu-id="30e66-113">関数が正常に完了しない場合は、[StrongNameErrorInfo](strongnameerrorinfo-function.md) 関数を呼び出して、最後に生成されたエラーを取得します。`StrongNameHashSize`</span><span class="sxs-lookup"><span data-stu-id="30e66-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e66-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="30e66-114">Requirements</span></span>  
 <span data-ttu-id="30e66-115">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e66-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e66-116">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="30e66-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="30e66-117">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="30e66-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30e66-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e66-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e66-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="30e66-119">See also</span></span>

- [<span data-ttu-id="30e66-120">StrongNameHashSize メソッド</span><span class="sxs-lookup"><span data-stu-id="30e66-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="30e66-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30e66-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
