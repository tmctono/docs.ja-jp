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
ms.openlocfilehash: 0c9adcc252fe16c95da8b2afca45bb2ee5dc545a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135205"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="d69e7-102">ICLRStrongName::GetHashFromBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="d69e7-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="d69e7-103">指定したハッシュ アルゴリズムを使用して、指定したメモリ アドレスにあるアセンブリのハッシュが取得されます。</span><span class="sxs-lookup"><span data-stu-id="d69e7-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d69e7-104">構文</span><span class="sxs-lookup"><span data-stu-id="d69e7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d69e7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d69e7-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="d69e7-106">からハッシュされるメモリブロックのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d69e7-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="d69e7-107">からメモリブロックの長さ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d69e7-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d69e7-108">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="d69e7-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d69e7-109">既定のアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="d69e7-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d69e7-110">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="d69e7-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d69e7-111">から要求された `pbHash`の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d69e7-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d69e7-112">入出力返された `pbHash`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d69e7-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d69e7-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="d69e7-113">Return Value</span></span>  
 <span data-ttu-id="d69e7-114">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](https://go.microsoft.com/fwlink/?LinkId=213878)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d69e7-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d69e7-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="d69e7-115">Requirements</span></span>  
 <span data-ttu-id="d69e7-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d69e7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d69e7-117">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="d69e7-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d69e7-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d69e7-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d69e7-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d69e7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d69e7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d69e7-120">See also</span></span>

- [<span data-ttu-id="d69e7-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d69e7-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
