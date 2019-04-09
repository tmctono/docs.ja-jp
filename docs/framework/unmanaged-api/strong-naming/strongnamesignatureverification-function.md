---
title: StrongNameSignatureVerification 関数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c398663b84637d2551b0d94bd59b9e0994721ba5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124768"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="43b74-102">StrongNameSignatureVerification 関数</span><span class="sxs-lookup"><span data-stu-id="43b74-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="43b74-103">指定したパスにあるアセンブリ マニフェストに厳密な名前の署名が含まれるかどうかを示す値が取得されます。これは指定したフラグに従って確認されます。</span><span class="sxs-lookup"><span data-stu-id="43b74-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="43b74-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="43b74-104">This function has been deprecated.</span></span> <span data-ttu-id="43b74-105">使用して、 [iclrstrongname::strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="43b74-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b74-106">構文</span><span class="sxs-lookup"><span data-stu-id="43b74-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43b74-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43b74-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="43b74-108">[in]確認するアセンブリのポータブル実行可能ファイル (.dll または .exe) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="43b74-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="43b74-109">[in]検証動作を変更するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="43b74-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="43b74-110">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="43b74-110">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="43b74-111">(0x00000001) - レジストリ設定を上書きする必要がある場合でも、強制的に検証します。</span><span class="sxs-lookup"><span data-stu-id="43b74-111">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="43b74-112">(0x00000002) - これが初めてマニフェストの検証であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="43b74-112">(0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="43b74-113">(0x00000004) のキャッシュで管理者特権を持つユーザーにのみアクセスを許可することを指定します。</span><span class="sxs-lookup"><span data-stu-id="43b74-113">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="43b74-114">(0x00000008) のアセンブリが現在のユーザーのみがアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="43b74-114">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="43b74-115">(0x00000010) - キャッシュはしないことを指定のアクセス制限を保証します。</span><span class="sxs-lookup"><span data-stu-id="43b74-115">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="43b74-116">(0x80000000) - 内部デバッグのために予約されています。</span><span class="sxs-lookup"><span data-stu-id="43b74-116">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="43b74-117">[out]厳密な名前の署名が検証されたかどうかを示すフラグです。</span><span class="sxs-lookup"><span data-stu-id="43b74-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="43b74-118">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="43b74-118">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="43b74-119">(0x00000001) - この値に設定が`false`レジストリ設定のために、検証が成功したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="43b74-119">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43b74-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="43b74-120">Return Value</span></span>  
 `true` <span data-ttu-id="43b74-121">検証が成功した場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="43b74-121">if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b74-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="43b74-122">Requirements</span></span>  
 <span data-ttu-id="43b74-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43b74-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43b74-124">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="43b74-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="43b74-125">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="43b74-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="43b74-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="43b74-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43b74-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="43b74-127">See also</span></span>

- [<span data-ttu-id="43b74-128">StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="43b74-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="43b74-129">StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="43b74-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="43b74-130">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43b74-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
