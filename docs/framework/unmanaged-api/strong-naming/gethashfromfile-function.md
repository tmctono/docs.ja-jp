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
ms.openlocfilehash: 5774b7cdcfedfc407b626ab5052f5b4a77461e9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049389"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="c79bf-102">GetHashFromFile 関数</span><span class="sxs-lookup"><span data-stu-id="c79bf-102">GetHashFromFile Function</span></span>
<span data-ttu-id="c79bf-103">指定したファイルの内容に対してハッシュが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c79bf-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="c79bf-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="c79bf-104">This function has been deprecated.</span></span> <span data-ttu-id="c79bf-105">使用して、 [iclrstrongname::gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="c79bf-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c79bf-106">構文</span><span class="sxs-lookup"><span data-stu-id="c79bf-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c79bf-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c79bf-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="c79bf-108">[in]ハッシュするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c79bf-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="c79bf-109">[入力、出力]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="c79bf-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="c79bf-110">有効なアルゴリズムを使用して、Win32 CryptoAPI で定義されています。</span><span class="sxs-lookup"><span data-stu-id="c79bf-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="c79bf-111">場合`piHashAlg`CALG_SHA 1 が使用される既定のアルゴリズムを 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c79bf-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="c79bf-112">[out]生成されたハッシュを含むバイト配列。</span><span class="sxs-lookup"><span data-stu-id="c79bf-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="c79bf-113">[in]バッファーの最大サイズを`pbHash`を指します。</span><span class="sxs-lookup"><span data-stu-id="c79bf-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="c79bf-114">[out]サイズ (バイト単位)、返された`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="c79bf-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c79bf-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="c79bf-115">Remarks</span></span>  
 <span data-ttu-id="c79bf-116">この関数は、同じ[GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)ファイル名の指定が Unicode ではなく ANSI を点が異なります。</span><span class="sxs-lookup"><span data-stu-id="c79bf-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c79bf-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="c79bf-117">Requirements</span></span>  
 <span data-ttu-id="c79bf-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c79bf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c79bf-119">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c79bf-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c79bf-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c79bf-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c79bf-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c79bf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79bf-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c79bf-122">See also</span></span>

- [<span data-ttu-id="c79bf-123">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="c79bf-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="c79bf-124">GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="c79bf-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="c79bf-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c79bf-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
