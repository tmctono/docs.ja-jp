---
title: ICLRStrongName::StrongNameHashSize メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: 0f4fdcbdfb9db7664920a42b9406a58f9c2de0b8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763112"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="3c01f-102">ICLRStrongName::StrongNameHashSize メソッド</span><span class="sxs-lookup"><span data-stu-id="3c01f-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="3c01f-103">指定したハッシュ アルゴリズムを使用して、ハッシュに必須のバッファー サイズが取得されます。</span><span class="sxs-lookup"><span data-stu-id="3c01f-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c01f-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c01f-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c01f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c01f-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="3c01f-106">からバッファーサイズを計算するために使用されるハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="3c01f-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="3c01f-107">入出力返されたバッファーサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="3c01f-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c01f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="3c01f-108">Return Value</span></span>  
 <span data-ttu-id="3c01f-109">`S_OK`メソッドが正常に完了した場合は。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3c01f-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c01f-110">要件</span><span class="sxs-lookup"><span data-stu-id="3c01f-110">Requirements</span></span>  
 <span data-ttu-id="3c01f-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c01f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c01f-112">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="3c01f-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3c01f-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3c01f-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c01f-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c01f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c01f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c01f-115">See also</span></span>

- [<span data-ttu-id="3c01f-116">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c01f-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
