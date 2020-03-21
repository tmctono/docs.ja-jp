---
title: ICLRStrongName::GetHashFromFileW メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 8f2d74531233f2ba423c39126ddc43e499cbb5d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176371"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="48b96-102">ICLRStrongName::GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="48b96-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="48b96-103">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="48b96-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48b96-104">構文</span><span class="sxs-lookup"><span data-stu-id="48b96-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="48b96-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48b96-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="48b96-106">[in]ハッシュするファイルの Unicode 名。</span><span class="sxs-lookup"><span data-stu-id="48b96-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="48b96-107">[イン、アウト]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="48b96-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="48b96-108">有効なアルゴリズムは、Win32 CryptoAPI によって定義されるアルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="48b96-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="48b96-109">0`piHashAlg`に設定すると、デフォルトのアルゴリズム CALG_SHA-1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="48b96-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="48b96-110">[アウト]生成されたハッシュを含むバイト配列。</span><span class="sxs-lookup"><span data-stu-id="48b96-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="48b96-111">[in]が`pbHash`指すバッファの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="48b96-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="48b96-112">[アウト]のサイズ (バイト単位)`pbHash`です。</span><span class="sxs-lookup"><span data-stu-id="48b96-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48b96-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="48b96-113">Return Value</span></span>  
 <span data-ttu-id="48b96-114">`S_OK`メソッドが正常に完了した場合。それ以外の場合は、失敗を示す HRESULT 値です (リストの[HRESULT の共通値](/windows/win32/seccrypto/common-hresult-values)を参照)。</span><span class="sxs-lookup"><span data-stu-id="48b96-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48b96-115">解説</span><span class="sxs-lookup"><span data-stu-id="48b96-115">Remarks</span></span>  
 <span data-ttu-id="48b96-116">このメソッドは、ファイル名の指定が ANSI ではなく Unicode であることを除いて[、ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="48b96-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48b96-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="48b96-117">Requirements</span></span>  
 <span data-ttu-id="48b96-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48b96-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48b96-119">**ヘッダー:** メタホスト.h</span><span class="sxs-lookup"><span data-stu-id="48b96-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="48b96-120">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="48b96-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48b96-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48b96-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b96-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="48b96-122">See also</span></span>

- [<span data-ttu-id="48b96-123">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="48b96-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="48b96-124">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48b96-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
