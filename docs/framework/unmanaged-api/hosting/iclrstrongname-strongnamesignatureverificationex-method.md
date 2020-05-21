---
title: ICLRStrongName::StrongNameSignatureVerificationEx メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
ms.openlocfilehash: e2003ce78f04b101fe093867e0820f9c3840151a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762709"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="d67e3-102">ICLRStrongName::StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="d67e3-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="d67e3-103">指定したパスにあるアセンブリマニフェストに厳密な名前の署名が含まれているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d67e3-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67e3-104">構文</span><span class="sxs-lookup"><span data-stu-id="d67e3-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d67e3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d67e3-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d67e3-106">から検証するアセンブリの移植可能な実行可能ファイル (.exe または .dll) のパス。</span><span class="sxs-lookup"><span data-stu-id="d67e3-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="d67e3-107">[入力] `true`レジストリ設定を上書きする必要がある場合でも、検証を実行するにはそれ以外の場合は `false` 。</span><span class="sxs-lookup"><span data-stu-id="d67e3-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="d67e3-108">[出力] `true`厳密な名前の署名が検証された場合は。それ以外の場合は `false` 。</span><span class="sxs-lookup"><span data-stu-id="d67e3-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="d67e3-109">`pfWasVerified``false`レジストリ設定によって検証が成功した場合は、もに設定されます。</span><span class="sxs-lookup"><span data-stu-id="d67e3-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d67e3-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d67e3-110">Return Value</span></span>  
 <span data-ttu-id="d67e3-111">`S_OK`検証が成功した場合は、それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d67e3-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d67e3-112">解説</span><span class="sxs-lookup"><span data-stu-id="d67e3-112">Remarks</span></span>  
 <span data-ttu-id="d67e3-113">[ICLRStrongName:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md)メソッドには、 [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)メソッドと同様の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d67e3-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="d67e3-114">ただし、 [ICLRStrongName:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md)の2番目の入力パラメーターと出力パラメーターは、 `BOOLEAN` の代わりに型に `DWORD` なります。</span><span class="sxs-lookup"><span data-stu-id="d67e3-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d67e3-115">要件</span><span class="sxs-lookup"><span data-stu-id="d67e3-115">Requirements</span></span>  
 <span data-ttu-id="d67e3-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67e3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67e3-117">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="d67e3-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d67e3-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d67e3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d67e3-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d67e3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67e3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d67e3-120">See also</span></span>

- [<span data-ttu-id="d67e3-121">StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="d67e3-121">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="d67e3-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d67e3-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
