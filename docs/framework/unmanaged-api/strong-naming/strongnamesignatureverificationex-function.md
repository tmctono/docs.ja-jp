---
title: StrongNameSignatureVerificationEx 関数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798922"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="fc076-102">StrongNameSignatureVerificationEx 関数</span><span class="sxs-lookup"><span data-stu-id="fc076-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="fc076-103">指定したパスにあるアセンブリ マニフェストに厳密な名前の署名が含まれるかどうかを示す値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="fc076-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="fc076-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="fc076-104">This function has been deprecated.</span></span> <span data-ttu-id="fc076-105">代わりに[ICLRStrongName:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fc076-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc076-106">構文</span><span class="sxs-lookup"><span data-stu-id="fc076-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc076-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc076-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="fc076-108">から検証するアセンブリの移植可能な実行可能ファイル (.exe または .dll) のパス。</span><span class="sxs-lookup"><span data-stu-id="fc076-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="fc076-109">からレジストリ設定を上書きする必要がある場合でも検証を実行する場合`false`は。それ以外の場合は。 `true`</span><span class="sxs-lookup"><span data-stu-id="fc076-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="fc076-110">入出力厳密な名前の署名が検証された`false`場合は。それ以外の場合は。 `true`</span><span class="sxs-lookup"><span data-stu-id="fc076-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="fc076-111">`pfWasVerified`レジストリ設定によっ`false`て検証が成功した場合は、もに設定されます。</span><span class="sxs-lookup"><span data-stu-id="fc076-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc076-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="fc076-112">Return Value</span></span>  
 <span data-ttu-id="fc076-113">`true`検証が成功した場合は、それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="fc076-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc076-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc076-114">Remarks</span></span>  
 <span data-ttu-id="fc076-115">`StrongNameSignatureVerificationEx`[StrongNameSignatureVerification](strongnamesignatureverification-function.md)関数と同様の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc076-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="fc076-116">ただし、2番目の入力パラメーターとの`StrongNameSignatureVerificationEx`出力パラメーターは、の`DWORD`代わりに型`BOOLEAN`になります。</span><span class="sxs-lookup"><span data-stu-id="fc076-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc076-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc076-117">Requirements</span></span>  
 <span data-ttu-id="fc076-118">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc076-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc076-119">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="fc076-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fc076-120">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="fc076-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="fc076-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc076-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc076-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc076-122">See also</span></span>

- [<span data-ttu-id="fc076-123">StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="fc076-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="fc076-124">StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="fc076-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="fc076-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc076-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
