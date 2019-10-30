---
title: ICLRStrongName::StrongNameGetBlobFromImage メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: ad3b151165eb233bd3a4a78d8f4d612a696b7e93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135093"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="9effe-102">ICLRStrongName::StrongNameGetBlobFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="9effe-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="9effe-103">指定したメモリ アドレスにあるアセンブリ イメージのバイナリ表現が取得されます。</span><span class="sxs-lookup"><span data-stu-id="9effe-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9effe-104">構文</span><span class="sxs-lookup"><span data-stu-id="9effe-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9effe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9effe-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="9effe-106">からマップされたアセンブリマニフェストのメモリアドレス。</span><span class="sxs-lookup"><span data-stu-id="9effe-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9effe-107">から`pbBase`にあるイメージのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="9effe-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="9effe-108">からイメージのバイナリ表現を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="9effe-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="9effe-109">[入力、出力]`pbBlob`の要求された最大サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="9effe-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="9effe-110">返されたときに、`pbBlob`の実際のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="9effe-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9effe-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="9effe-111">Return Value</span></span>  
 <span data-ttu-id="9effe-112">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](https://go.microsoft.com/fwlink/?LinkId=213878)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9effe-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9effe-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="9effe-113">Requirements</span></span>  
 <span data-ttu-id="9effe-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9effe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9effe-115">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="9effe-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9effe-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9effe-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9effe-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9effe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9effe-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9effe-118">See also</span></span>

- [<span data-ttu-id="9effe-119">StrongNameGetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="9effe-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="9effe-120">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9effe-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
