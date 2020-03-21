---
title: GetHashFromFile 関数
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176982"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="31ef2-102">GetHashFromFile 関数</span><span class="sxs-lookup"><span data-stu-id="31ef2-102">GetHashFromFile Function</span></span>
<span data-ttu-id="31ef2-103">指定したファイルの内容に対してハッシュが生成されます。</span><span class="sxs-lookup"><span data-stu-id="31ef2-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="31ef2-104">この関数は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="31ef2-104">This function has been deprecated.</span></span> <span data-ttu-id="31ef2-105">代わりに[、](../hosting/iclrstrongname-gethashfromfile-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="31ef2-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31ef2-106">構文</span><span class="sxs-lookup"><span data-stu-id="31ef2-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31ef2-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31ef2-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="31ef2-108">[in]ハッシュするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="31ef2-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="31ef2-109">[イン、アウト]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="31ef2-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="31ef2-110">有効なアルゴリズムは、Win32 CryptoAPI によって定義されるアルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="31ef2-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="31ef2-111">0`piHashAlg`に設定すると、デフォルトのアルゴリズム CALG_SHA-1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="31ef2-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="31ef2-112">[アウト]生成されたハッシュを含むバイト配列。</span><span class="sxs-lookup"><span data-stu-id="31ef2-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="31ef2-113">[in]指す`pbHash`バッファーの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="31ef2-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="31ef2-114">[アウト]返された`pbHash`のサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="31ef2-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31ef2-115">解説</span><span class="sxs-lookup"><span data-stu-id="31ef2-115">Remarks</span></span>  
 <span data-ttu-id="31ef2-116">この関数は、ファイル名の指定が Unicode ではなく ANSI であることを除けば[、GetHashFromFileW](gethashfromfilew-function.md)と同じです。</span><span class="sxs-lookup"><span data-stu-id="31ef2-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31ef2-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="31ef2-117">Requirements</span></span>  
 <span data-ttu-id="31ef2-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ef2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31ef2-119">**ヘッダー:** ストロングネーム.h</span><span class="sxs-lookup"><span data-stu-id="31ef2-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="31ef2-120">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="31ef2-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31ef2-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31ef2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ef2-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="31ef2-122">See also</span></span>

- [<span data-ttu-id="31ef2-123">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="31ef2-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="31ef2-124">GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="31ef2-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="31ef2-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31ef2-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
