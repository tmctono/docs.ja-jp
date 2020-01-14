---
title: StrongNameSignatureVerificationEx2 メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
ms.openlocfilehash: 81640e8e34335898f4dd7f4f43eafbd3ef191d19
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938155"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="2e16a-102">StrongNameSignatureVerificationEx2 メソッド</span><span class="sxs-lookup"><span data-stu-id="2e16a-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="2e16a-103">厳密に名前が付けられたアセンブリの署名を検証し、ECMA キーから実際のキーへのマッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="2e16a-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e16a-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e16a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e16a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e16a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2e16a-106">から検証するアセンブリの移植可能な実行可能ファイル (.exe または .dll) のパス。</span><span class="sxs-lookup"><span data-stu-id="2e16a-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="2e16a-107">[入力] レジストリ設定を上書きする必要がある場合でも、検証を実行する `true` ます。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="2e16a-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="2e16a-108">からECMA 公開キーから、検証に使用される実際のキーへのマッピングへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2e16a-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="2e16a-109">から実際の ECMA 公開キーの長さ。</span><span class="sxs-lookup"><span data-stu-id="2e16a-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="2e16a-110">[out] 厳密な名前の署名が検証された場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="2e16a-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="2e16a-111">レジストリ設定によって検証が成功した場合は、このパラメーターも `false` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2e16a-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e16a-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="2e16a-112">Return Value</span></span>  
 <span data-ttu-id="2e16a-113">検証が成功した場合は `S_OK` します。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="2e16a-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e16a-114">要件</span><span class="sxs-lookup"><span data-stu-id="2e16a-114">Requirements</span></span>  
 <span data-ttu-id="2e16a-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e16a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e16a-116">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="2e16a-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2e16a-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2e16a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e16a-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e16a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e16a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e16a-119">See also</span></span>

- [<span data-ttu-id="2e16a-120">StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="2e16a-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="2e16a-121">StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="2e16a-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="2e16a-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e16a-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
