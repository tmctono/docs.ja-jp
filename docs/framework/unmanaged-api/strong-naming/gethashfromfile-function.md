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
ms.openlocfilehash: ffa25b1ec6fda80099f333c1d0a4cf57b76379e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140693"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="81aa8-102">GetHashFromFile 関数</span><span class="sxs-lookup"><span data-stu-id="81aa8-102">GetHashFromFile Function</span></span>
<span data-ttu-id="81aa8-103">指定したファイルの内容に対してハッシュが生成されます。</span><span class="sxs-lookup"><span data-stu-id="81aa8-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="81aa8-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="81aa8-104">This function has been deprecated.</span></span> <span data-ttu-id="81aa8-105">代わりに[ICLRStrongName:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="81aa8-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81aa8-106">構文</span><span class="sxs-lookup"><span data-stu-id="81aa8-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81aa8-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81aa8-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="81aa8-108">からハッシュするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="81aa8-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="81aa8-109">[入力、出力]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="81aa8-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="81aa8-110">有効なアルゴリズムは、Win32 CryptoAPI によって定義されているものです。</span><span class="sxs-lookup"><span data-stu-id="81aa8-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="81aa8-111">`piHashAlg` が0に設定されている場合は、既定のアルゴリズム CALG_SHA が使用されます。</span><span class="sxs-lookup"><span data-stu-id="81aa8-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="81aa8-112">入出力生成されたハッシュを格納しているバイト配列。</span><span class="sxs-lookup"><span data-stu-id="81aa8-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="81aa8-113">から`pbHash` が指すバッファーの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="81aa8-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="81aa8-114">入出力返された `pbHash`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="81aa8-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81aa8-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="81aa8-115">Remarks</span></span>  
 <span data-ttu-id="81aa8-116">この関数は[GetHashFromFileW](gethashfromfilew-function.md)と同じですが、ファイル名の指定は Unicode ではなく ANSI である点が異なります。</span><span class="sxs-lookup"><span data-stu-id="81aa8-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81aa8-117">［要件］</span><span class="sxs-lookup"><span data-stu-id="81aa8-117">Requirements</span></span>  
 <span data-ttu-id="81aa8-118">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81aa8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81aa8-119">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="81aa8-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="81aa8-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="81aa8-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81aa8-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81aa8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81aa8-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="81aa8-122">See also</span></span>

- [<span data-ttu-id="81aa8-123">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="81aa8-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="81aa8-124">GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="81aa8-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="81aa8-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81aa8-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
