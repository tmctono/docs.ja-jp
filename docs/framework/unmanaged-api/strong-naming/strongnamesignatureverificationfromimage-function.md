---
title: StrongNameSignatureVerificationFromImage 関数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9eef4e1b1c9c82d8576c01dd124ee9ac68c2583
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610040"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="f13f6-102">StrongNameSignatureVerificationFromImage 関数</span><span class="sxs-lookup"><span data-stu-id="f13f6-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="f13f6-103">メモリに既にマップされているアセンブリが、関連付けられている公開キーに対して有効であるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="f13f6-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="f13f6-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="f13f6-104">This function has been deprecated.</span></span> <span data-ttu-id="f13f6-105">使用して、 [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="f13f6-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f13f6-106">構文</span><span class="sxs-lookup"><span data-stu-id="f13f6-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f13f6-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f13f6-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="f13f6-108">[in]マップされているアセンブリ マニフェストの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="f13f6-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f13f6-109">[in]マップされたイメージのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="f13f6-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="f13f6-110">[in]検証の動作に影響するフラグ。</span><span class="sxs-lookup"><span data-stu-id="f13f6-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="f13f6-111">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f13f6-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="f13f6-112">`SN_INFLAG_FORCE_VER` (0x00000001) - レジストリ設定を上書きする必要がある場合でも、強制的に検証します。</span><span class="sxs-lookup"><span data-stu-id="f13f6-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="f13f6-113">`SN_INFLAG_INSTALL` (0x00000002) - これはこのイメージ上で実行される最初の認証であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f13f6-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="f13f6-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) のキャッシュで管理者特権を持つユーザーにのみアクセスを許可することを指定します。</span><span class="sxs-lookup"><span data-stu-id="f13f6-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="f13f6-115">`SN_INFLAG_USER_ACCESS` (0x00000008) のアセンブリが現在のユーザーのみがアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f13f6-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="f13f6-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - キャッシュはしないことを指定のアクセス制限を保証します。</span><span class="sxs-lookup"><span data-stu-id="f13f6-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="f13f6-117">`SN_INFLAG_RUNTIME` (0x80000000) - 内部デバッグのために予約されています。</span><span class="sxs-lookup"><span data-stu-id="f13f6-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="f13f6-118">[out]追加の出力情報用のフラグです。</span><span class="sxs-lookup"><span data-stu-id="f13f6-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="f13f6-119">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f13f6-119">The following value is supported:</span></span>  
  
- <span data-ttu-id="f13f6-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - この値に設定が`false`レジストリ設定のために、検証が成功したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="f13f6-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f13f6-121">戻り値</span><span class="sxs-lookup"><span data-stu-id="f13f6-121">Return Value</span></span>  
 <span data-ttu-id="f13f6-122">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="f13f6-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f13f6-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="f13f6-123">Remarks</span></span>  
 <span data-ttu-id="f13f6-124">場合、`StrongNameSignatureVerificationFromImage`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="f13f6-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f13f6-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="f13f6-125">Requirements</span></span>  
 <span data-ttu-id="f13f6-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f13f6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f13f6-127">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f13f6-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f13f6-128">**ライブラリ:** Mscoree.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f13f6-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="f13f6-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f13f6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f13f6-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f13f6-130">See also</span></span>

- [<span data-ttu-id="f13f6-131">StrongNameSignatureVerificationFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="f13f6-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="f13f6-132">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f13f6-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
