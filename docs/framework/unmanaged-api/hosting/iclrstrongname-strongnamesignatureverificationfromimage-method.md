---
title: ICLRStrongName::StrongNameSignatureVerificationFromImage メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7e09ac96a8803f41d78b532c9da67315e5dd6b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113738"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="3b54e-102">ICLRStrongName::StrongNameSignatureVerificationFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="3b54e-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="3b54e-103">メモリに既にマップされているアセンブリが、関連付けられている公開キーに対して有効であるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="3b54e-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b54e-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b54e-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b54e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b54e-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="3b54e-106">[in]マップされているアセンブリ マニフェストの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="3b54e-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="3b54e-107">[in]マップされたイメージのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="3b54e-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="3b54e-108">[in]検証の動作に影響するフラグ。</span><span class="sxs-lookup"><span data-stu-id="3b54e-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="3b54e-109">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3b54e-109">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="3b54e-110">(0x00000001) - レジストリ設定を上書きする必要がある場合でも、強制的に検証します。</span><span class="sxs-lookup"><span data-stu-id="3b54e-110">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="3b54e-111">(0x00000002) - これはこのイメージ上で実行される最初の認証であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b54e-111">(0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="3b54e-112">(0x00000004) のキャッシュで管理者特権を持つユーザーにのみアクセスを許可することを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b54e-112">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="3b54e-113">(0x00000008) のアセンブリが現在のユーザーのみがアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b54e-113">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="3b54e-114">(0x00000010) - キャッシュはしないことを指定のアクセス制限を保証します。</span><span class="sxs-lookup"><span data-stu-id="3b54e-114">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="3b54e-115">(0x80000000) - 内部デバッグのために予約されています。</span><span class="sxs-lookup"><span data-stu-id="3b54e-115">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="3b54e-116">[out]追加の出力情報用のフラグです。</span><span class="sxs-lookup"><span data-stu-id="3b54e-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="3b54e-117">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3b54e-117">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="3b54e-118">(0x00000001) - この値に設定が`false`レジストリ設定のために、検証が成功したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="3b54e-118">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b54e-119">戻り値</span><span class="sxs-lookup"><span data-stu-id="3b54e-119">Return Value</span></span>  
 `S_OK` <span data-ttu-id="3b54e-120">メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="3b54e-120">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b54e-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b54e-121">Requirements</span></span>  
 <span data-ttu-id="3b54e-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b54e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b54e-123">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3b54e-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3b54e-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3b54e-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3b54e-125">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3b54e-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b54e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b54e-126">See also</span></span>

- [<span data-ttu-id="3b54e-127">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b54e-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
