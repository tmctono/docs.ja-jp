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
ms.openlocfilehash: b09677a45c5d515aacb2cac709599140039a9dd8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899552"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="9a414-102">ICLRStrongName::StrongNameKeyGenEx メソッド</span><span class="sxs-lookup"><span data-stu-id="9a414-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="9a414-103">厳密な名前の使用のために、指定されたキーサイズを持つ新しい公開/秘密キーのペアを生成します。</span><span class="sxs-lookup"><span data-stu-id="9a414-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a414-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a414-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a414-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a414-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="9a414-106">から要求されたキーコンテナー名。</span><span class="sxs-lookup"><span data-stu-id="9a414-106">[in] The requested key container name.</span></span> <span data-ttu-id="9a414-107">`wszKeyContainer` は、空でない文字列であるか、または一時名を生成するために null である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a414-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9a414-108">からキーを登録したままにするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="9a414-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="9a414-109">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9a414-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="9a414-110">0x00000000-一時キーコンテナー名を生成するために `wszKeyContainer` が null の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="9a414-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="9a414-111">0x00000001 (`SN_LEAVE_KEY`)-キーを登録したままにすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a414-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="9a414-112">から要求されたキーのサイズ (ビット単位)。</span><span class="sxs-lookup"><span data-stu-id="9a414-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="9a414-113">入出力返された公開/秘密キーのペア。</span><span class="sxs-lookup"><span data-stu-id="9a414-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="9a414-114">入出力`ppbKeyBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="9a414-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a414-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="9a414-115">Return Value</span></span>  
 <span data-ttu-id="9a414-116">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9a414-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a414-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a414-117">Remarks</span></span>  
 <span data-ttu-id="9a414-118">.NET Framework バージョン1.0 および1.1 では、厳密な名前でアセンブリに署名するには、1024ビットの `dwKeySize` が必要です。バージョン2.0 では、2048ビットキーのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="9a414-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="9a414-119">キーを取得した後、 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッドを呼び出して、割り当てられたメモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a414-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a414-120">要件</span><span class="sxs-lookup"><span data-stu-id="9a414-120">Requirements</span></span>  
 <span data-ttu-id="9a414-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a414-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a414-122">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="9a414-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9a414-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9a414-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a414-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a414-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a414-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a414-125">See also</span></span>

- [<span data-ttu-id="9a414-126">StrongNameKeyGen メソッド</span><span class="sxs-lookup"><span data-stu-id="9a414-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="9a414-127">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a414-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
