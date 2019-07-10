---
title: ICLRStrongName::GetHashFromBlob メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4839f098a41e0d2b8e87616791b69ffd83e139f0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748193"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="d67f1-102">ICLRStrongName::GetHashFromBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="d67f1-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="d67f1-103">指定したハッシュ アルゴリズムを使用して、指定したメモリ アドレスにあるアセンブリのハッシュが取得されます。</span><span class="sxs-lookup"><span data-stu-id="d67f1-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="d67f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d67f1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d67f1-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="d67f1-106">[in]ハッシュされるメモリ ブロックのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d67f1-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="d67f1-107">[in]メモリ ブロックの長さ、(バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d67f1-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d67f1-108">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="d67f1-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d67f1-109">既定のアルゴリズムに 0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="d67f1-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d67f1-110">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="d67f1-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d67f1-111">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="d67f1-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d67f1-112">[out]サイズ (バイト単位)、返された`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="d67f1-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d67f1-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="d67f1-113">Return Value</span></span>  
 <span data-ttu-id="d67f1-114">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="d67f1-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d67f1-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="d67f1-115">Requirements</span></span>  
 <span data-ttu-id="d67f1-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67f1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67f1-117">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d67f1-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d67f1-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d67f1-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d67f1-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d67f1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67f1-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d67f1-120">See also</span></span>

- [<span data-ttu-id="d67f1-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d67f1-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
