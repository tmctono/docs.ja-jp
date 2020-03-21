---
title: GetHashFromFileW 関数
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
ms.openlocfilehash: 9db583c7064cb910b29e84437f31143dac0d3ec9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175084"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="fd7af-102">GetHashFromFileW 関数</span><span class="sxs-lookup"><span data-stu-id="fd7af-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="fd7af-103">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fd7af-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="fd7af-104">この関数は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="fd7af-104">This function has been deprecated.</span></span> <span data-ttu-id="fd7af-105">代わりに[、メソッド](../hosting/iclrstrongname-gethashfromfilew-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd7af-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7af-106">構文</span><span class="sxs-lookup"><span data-stu-id="fd7af-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="fd7af-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd7af-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="fd7af-108">[in]ハッシュするファイルの Unicode 名。</span><span class="sxs-lookup"><span data-stu-id="fd7af-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="fd7af-109">[イン、アウト]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="fd7af-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="fd7af-110">有効なアルゴリズムは、Win32 CryptoAPI によって定義されるアルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="fd7af-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="fd7af-111">0`piHashAlg`に設定すると、デフォルトのアルゴリズム CALG_SHA-1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd7af-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="fd7af-112">[アウト]生成されたハッシュを含むバイト配列。</span><span class="sxs-lookup"><span data-stu-id="fd7af-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="fd7af-113">[in]が`pbHash`指すバッファの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="fd7af-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="fd7af-114">[アウト]のサイズ (バイト単位)`pbHash`です。</span><span class="sxs-lookup"><span data-stu-id="fd7af-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd7af-115">解説</span><span class="sxs-lookup"><span data-stu-id="fd7af-115">Remarks</span></span>  
 <span data-ttu-id="fd7af-116">この関数は、ファイル名指定が ANSI ではなくユニコードであることを除けば[、GetHashFromFile](gethashfromfile-function.md)と同じです。</span><span class="sxs-lookup"><span data-stu-id="fd7af-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd7af-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="fd7af-117">Requirements</span></span>  
 <span data-ttu-id="fd7af-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd7af-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd7af-119">**ヘッダー:** ストロングネーム.h</span><span class="sxs-lookup"><span data-stu-id="fd7af-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fd7af-120">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="fd7af-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd7af-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd7af-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7af-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd7af-122">See also</span></span>

- [<span data-ttu-id="fd7af-123">GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="fd7af-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="fd7af-124">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="fd7af-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="fd7af-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd7af-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
