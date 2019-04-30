---
title: ICLRStrongName::StrongNameKeyGenEx メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97e6f16029b9a273a68d52b830939819bfa5380
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993032"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="da44c-102">ICLRStrongName::StrongNameKeyGenEx メソッド</span><span class="sxs-lookup"><span data-stu-id="da44c-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="da44c-103">指定されたキー サイズ、厳密な名前を使用して新しい公開/秘密キー ペアを生成します。</span><span class="sxs-lookup"><span data-stu-id="da44c-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da44c-104">構文</span><span class="sxs-lookup"><span data-stu-id="da44c-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da44c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da44c-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="da44c-106">[in]要求されたキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="da44c-106">[in] The requested key container name.</span></span> <span data-ttu-id="da44c-107">`wszKeyContainer` 空でない文字列または一時的な名前を生成する null であること。</span><span class="sxs-lookup"><span data-stu-id="da44c-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="da44c-108">[in]登録されているキーのままにするかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="da44c-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="da44c-109">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="da44c-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="da44c-110">0x00000000 の際に使用される`wszKeyContainer`一時的なキー コンテナーの名前を生成する場合は null です。</span><span class="sxs-lookup"><span data-stu-id="da44c-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="da44c-111">0x00000001 (`SN_LEAVE_KEY`) のキーを左に登録する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="da44c-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="da44c-112">[in]ビット単位で、キーの要求されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="da44c-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="da44c-113">[out]返された公開/秘密キー ペア。</span><span class="sxs-lookup"><span data-stu-id="da44c-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="da44c-114">[out]サイズ (バイト単位) の`ppbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="da44c-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da44c-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="da44c-115">Return Value</span></span>  
 <span data-ttu-id="da44c-116">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="da44c-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da44c-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="da44c-117">Remarks</span></span>  
 <span data-ttu-id="da44c-118">.NET Framework バージョン 1.0 および 1.1 が必要です、 `dwKeySize` version 2.0 を 1024 ビットです。 厳密な名前でアセンブリに署名するには、2048 ビットのキーのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="da44c-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="da44c-119">呼び出す必要があります、キーが取得された後、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)を割り当てられたメモリを解放するメソッド。</span><span class="sxs-lookup"><span data-stu-id="da44c-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da44c-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="da44c-120">Requirements</span></span>  
 <span data-ttu-id="da44c-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da44c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da44c-122">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="da44c-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="da44c-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="da44c-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da44c-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da44c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da44c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="da44c-125">See also</span></span>

- [<span data-ttu-id="da44c-126">StrongNameKeyGen メソッド</span><span class="sxs-lookup"><span data-stu-id="da44c-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="da44c-127">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da44c-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
