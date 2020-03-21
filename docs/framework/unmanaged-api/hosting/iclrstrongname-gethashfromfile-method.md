---
title: ICLRStrongName::GetHashFromFile メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: ed735c3d7830551581df35793f3f6fdc4953dc8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178074"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="e7c5c-102">ICLRStrongName::GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="e7c5c-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="e7c5c-103">指定したファイルの内容に対してハッシュが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7c5c-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7c5c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7c5c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7c5c-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="e7c5c-106">[in]ハッシュするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="e7c5c-107">[イン、アウト]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="e7c5c-108">有効なアルゴリズムは、Win32 CryptoAPI によって定義されるアルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="e7c5c-109">0`piHashAlg`に設定すると、デフォルトのアルゴリズム CALG_SHA-1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="e7c5c-110">[アウト]生成されたハッシュを含むバイト配列。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="e7c5c-111">[in]指す`pbHash`バッファーの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="e7c5c-112">[アウト]返された`pbHash`のサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="e7c5c-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7c5c-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="e7c5c-113">Return Value</span></span>  
 <span data-ttu-id="e7c5c-114">`S_OK`メソッドが正常に完了した場合。それ以外の場合は、失敗を示す HRESULT 値です (リストの[HRESULT の共通値](/windows/win32/seccrypto/common-hresult-values)を参照)。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7c5c-115">解説</span><span class="sxs-lookup"><span data-stu-id="e7c5c-115">Remarks</span></span>  
 <span data-ttu-id="e7c5c-116">このメソッドは、ファイル名の指定が Unicode ではなく ANSI であることを除いて[、ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7c5c-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="e7c5c-117">Requirements</span></span>  
 <span data-ttu-id="e7c5c-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7c5c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7c5c-119">**ヘッダー:** メタホスト.h</span><span class="sxs-lookup"><span data-stu-id="e7c5c-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e7c5c-120">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="e7c5c-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7c5c-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7c5c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c5c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7c5c-122">See also</span></span>

- [<span data-ttu-id="e7c5c-123">GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="e7c5c-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="e7c5c-124">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7c5c-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
