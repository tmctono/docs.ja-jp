---
title: ICLRStrongName::StrongNameSignatureVerification メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
ms.openlocfilehash: 6375fd8e4a314403267a4cdf2e8356677e9e7a06
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899482"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="4a3d9-102">ICLRStrongName::StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="4a3d9-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="4a3d9-103">指定したパスにあるアセンブリマニフェストに厳密な名前の署名が含まれているかどうかを示す値を取得します。この署名は、指定したフラグに従って検証されます。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a3d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a3d9-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a3d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a3d9-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4a3d9-106">から検証するアセンブリの移植可能な実行可能ファイル (.dll または .exe) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="4a3d9-107">から検証動作を変更するフラグ。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="4a3d9-108">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="4a3d9-109">`SN_INFLAG_FORCE_VER` (0x00000001)-レジストリ設定を上書きする必要がある場合でも、検証を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="4a3d9-110">`SN_INFLAG_INSTALL` (0x00000002)-マニフェストを初めて検証するときにこれを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="4a3d9-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-キャッシュが管理者特権を持つユーザーにのみアクセスを許可することを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="4a3d9-112">`SN_INFLAG_USER_ACCESS` (0x00000008)-現在のユーザーのみがアセンブリにアクセスできるように指定します。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="4a3d9-113">`SN_INFLAG_ALL_ACCESS` (0x00000010)-キャッシュがアクセス制限の保証を提供しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="4a3d9-114">`SN_INFLAG_RUNTIME` (0x80000000)-内部デバッグ用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="4a3d9-115">入出力厳密な名前の署名が検証されたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="4a3d9-116">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-116">The following value is supported:</span></span>  
  
- <span data-ttu-id="4a3d9-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-この値は `false` に設定され、レジストリ設定によって検証が成功したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a3d9-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="4a3d9-118">Return Value</span></span>  
 <span data-ttu-id="4a3d9-119">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a3d9-120">要件</span><span class="sxs-lookup"><span data-stu-id="4a3d9-120">Requirements</span></span>  
 <span data-ttu-id="4a3d9-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a3d9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a3d9-122">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="4a3d9-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4a3d9-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4a3d9-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a3d9-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a3d9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a3d9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a3d9-125">See also</span></span>

- [<span data-ttu-id="4a3d9-126">StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="4a3d9-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="4a3d9-127">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a3d9-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
