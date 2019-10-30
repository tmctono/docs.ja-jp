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
ms.openlocfilehash: db6f39119d143d27c0d3a80a9c65565d4dfd0d39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140678"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="2d0c9-102">GetHashFromFileW 関数</span><span class="sxs-lookup"><span data-stu-id="2d0c9-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="2d0c9-103">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="2d0c9-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-104">This function has been deprecated.</span></span> <span data-ttu-id="2d0c9-105">代わりに[ICLRStrongName:: GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d0c9-106">構文</span><span class="sxs-lookup"><span data-stu-id="2d0c9-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="2d0c9-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d0c9-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2d0c9-108">からハッシュするファイルの Unicode 名。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2d0c9-109">[入力、出力]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="2d0c9-110">有効なアルゴリズムは、Win32 CryptoAPI によって定義されているものです。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="2d0c9-111">`piHashAlg` が0に設定されている場合は、既定のアルゴリズム CALG_SHA が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2d0c9-112">入出力生成されたハッシュを格納しているバイト配列。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2d0c9-113">から`pbHash`が指すバッファーの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2d0c9-114">入出力`pbHash`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d0c9-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d0c9-115">Remarks</span></span>  
 <span data-ttu-id="2d0c9-116">この関数は[GetHashFromFile](gethashfromfile-function.md)と同じですが、ファイル名の指定は ANSI ではなく Unicode である点が異なります。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d0c9-117">［要件］</span><span class="sxs-lookup"><span data-stu-id="2d0c9-117">Requirements</span></span>  
 <span data-ttu-id="2d0c9-118">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d0c9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d0c9-119">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="2d0c9-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2d0c9-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2d0c9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2d0c9-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d0c9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d0c9-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d0c9-122">See also</span></span>

- [<span data-ttu-id="2d0c9-123">GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="2d0c9-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="2d0c9-124">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="2d0c9-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="2d0c9-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d0c9-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
