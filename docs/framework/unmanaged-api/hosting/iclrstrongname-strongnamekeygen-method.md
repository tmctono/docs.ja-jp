---
title: ICLRStrongName::StrongNameKeyGen メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c535d3d73b6d3d0165ea2d744ef625a16bd76cd4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747834"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="df195-102">ICLRStrongName::StrongNameKeyGen メソッド</span><span class="sxs-lookup"><span data-stu-id="df195-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="df195-103">厳密な名前を使用するために新しい公開/秘密キーの組が作成されます。</span><span class="sxs-lookup"><span data-stu-id="df195-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df195-104">構文</span><span class="sxs-lookup"><span data-stu-id="df195-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df195-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df195-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="df195-106">[in]要求されたキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="df195-106">[in] The requested key container name.</span></span> <span data-ttu-id="df195-107">`wszKeyContainer` 空でない文字列または一時的な名前を生成する null であること。</span><span class="sxs-lookup"><span data-stu-id="df195-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="df195-108">[in]登録されているキーのままにするかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="df195-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="df195-109">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df195-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="df195-110">0x00000000 の際に使用される`wszKeyContainer`一時的なキー コンテナーの名前を生成する場合は null です。</span><span class="sxs-lookup"><span data-stu-id="df195-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="df195-111">0x00000001 (`SN_LEAVE_KEY`) のキーを左に登録する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="df195-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="df195-112">[out]返された公開/秘密キー ペア。</span><span class="sxs-lookup"><span data-stu-id="df195-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="df195-113">[out]サイズ (バイト単位) の`ppbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="df195-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df195-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="df195-114">Return Value</span></span>  
 <span data-ttu-id="df195-115">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="df195-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df195-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="df195-116">Remarks</span></span>  
 <span data-ttu-id="df195-117">[Iclrstrongname::strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)メソッドは、1024 ビットのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="df195-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="df195-118">呼び出す必要があります、キーが取得された後、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)を割り当てられたメモリを解放するメソッド。</span><span class="sxs-lookup"><span data-stu-id="df195-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df195-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="df195-119">Requirements</span></span>  
 <span data-ttu-id="df195-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df195-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df195-121">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="df195-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="df195-122">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="df195-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df195-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df195-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df195-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="df195-124">See also</span></span>

- [<span data-ttu-id="df195-125">StrongNameKeyGenEx メソッド</span><span class="sxs-lookup"><span data-stu-id="df195-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="df195-126">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df195-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
