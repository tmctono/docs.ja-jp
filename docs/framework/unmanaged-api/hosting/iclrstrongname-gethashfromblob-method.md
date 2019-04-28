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
ms.openlocfilehash: f84d50579feade09df1b42a8e2f0c6b3e6a94fac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771658"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="bc6b5-102">ICLRStrongName::GetHashFromBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="bc6b5-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="bc6b5-103">指定したハッシュ アルゴリズムを使用して、指定したメモリ アドレスにあるアセンブリのハッシュが取得されます。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc6b5-104">構文</span><span class="sxs-lookup"><span data-stu-id="bc6b5-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc6b5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc6b5-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="bc6b5-106">[in]ハッシュされるメモリ ブロックのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="bc6b5-107">[in]メモリ ブロックの長さ、(バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="bc6b5-108">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="bc6b5-109">既定のアルゴリズムに 0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="bc6b5-110">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="bc6b5-111">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="bc6b5-112">[out]サイズ (バイト単位)、返された`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc6b5-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="bc6b5-113">Return Value</span></span>  
 <span data-ttu-id="bc6b5-114">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc6b5-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="bc6b5-115">Requirements</span></span>  
 <span data-ttu-id="bc6b5-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc6b5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc6b5-117">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bc6b5-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bc6b5-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bc6b5-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc6b5-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc6b5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc6b5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc6b5-120">See also</span></span>

- [<span data-ttu-id="bc6b5-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc6b5-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
