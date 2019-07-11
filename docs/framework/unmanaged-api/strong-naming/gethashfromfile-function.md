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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38c663bc2db780c89ca666702534a75525ae189b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771959"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="9eb9a-102">GetHashFromFile 関数</span><span class="sxs-lookup"><span data-stu-id="9eb9a-102">GetHashFromFile Function</span></span>
<span data-ttu-id="9eb9a-103">指定したファイルの内容に対してハッシュが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="9eb9a-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-104">This function has been deprecated.</span></span> <span data-ttu-id="9eb9a-105">使用して、 [iclrstrongname::gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb9a-106">構文</span><span class="sxs-lookup"><span data-stu-id="9eb9a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eb9a-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9eb9a-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="9eb9a-108">[in]ハッシュするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9eb9a-109">[入力、出力]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="9eb9a-110">有効なアルゴリズムを使用して、Win32 CryptoAPI で定義されています。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="9eb9a-111">場合`piHashAlg`CALG_SHA 1 が使用される既定のアルゴリズムを 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9eb9a-112">[out]生成されたハッシュを含むバイト配列。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9eb9a-113">[in]バッファーの最大サイズを`pbHash`を指します。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9eb9a-114">[out]サイズ (バイト単位)、返された`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9eb9a-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="9eb9a-115">Remarks</span></span>  
 <span data-ttu-id="9eb9a-116">この関数は、同じ[GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)ファイル名の指定が Unicode ではなく ANSI を点が異なります。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eb9a-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="9eb9a-117">Requirements</span></span>  
 <span data-ttu-id="9eb9a-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb9a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eb9a-119">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9eb9a-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9eb9a-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9eb9a-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9eb9a-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eb9a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb9a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9eb9a-122">See also</span></span>

- [<span data-ttu-id="9eb9a-123">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="9eb9a-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="9eb9a-124">GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="9eb9a-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="9eb9a-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9eb9a-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
