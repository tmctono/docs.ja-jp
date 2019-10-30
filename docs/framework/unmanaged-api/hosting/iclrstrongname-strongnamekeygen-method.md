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
ms.openlocfilehash: 4f3574e282d24fa11ffa2f85463f682c42098ae7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135049"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="6fab9-102">ICLRStrongName::StrongNameKeyGen メソッド</span><span class="sxs-lookup"><span data-stu-id="6fab9-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="6fab9-103">厳密な名前を使用するために新しい公開/秘密キーの組が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6fab9-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fab9-104">構文</span><span class="sxs-lookup"><span data-stu-id="6fab9-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fab9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fab9-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="6fab9-106">から要求されたキーコンテナー名。</span><span class="sxs-lookup"><span data-stu-id="6fab9-106">[in] The requested key container name.</span></span> <span data-ttu-id="6fab9-107">`wszKeyContainer` は、空でない文字列であるか、または一時名を生成するために null である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fab9-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6fab9-108">からキーを登録したままにするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="6fab9-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="6fab9-109">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6fab9-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="6fab9-110">0x00000000-一時キーコンテナー名を生成するために `wszKeyContainer` が null の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6fab9-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="6fab9-111">0x00000001 (`SN_LEAVE_KEY`)-キーを登録したままにすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="6fab9-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="6fab9-112">入出力返された公開/秘密キーのペア。</span><span class="sxs-lookup"><span data-stu-id="6fab9-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="6fab9-113">入出力`ppbKeyBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6fab9-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fab9-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="6fab9-114">Return Value</span></span>  
 <span data-ttu-id="6fab9-115">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](https://go.microsoft.com/fwlink/?LinkId=213878)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="6fab9-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fab9-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="6fab9-116">Remarks</span></span>  
 <span data-ttu-id="6fab9-117">[ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)メソッドは、1024ビットのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fab9-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="6fab9-118">キーを取得した後、 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッドを呼び出して、割り当てられたメモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fab9-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fab9-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="6fab9-119">Requirements</span></span>  
 <span data-ttu-id="6fab9-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fab9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fab9-121">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="6fab9-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6fab9-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6fab9-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fab9-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fab9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fab9-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fab9-124">See also</span></span>

- [<span data-ttu-id="6fab9-125">StrongNameKeyGenEx メソッド</span><span class="sxs-lookup"><span data-stu-id="6fab9-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="6fab9-126">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fab9-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
