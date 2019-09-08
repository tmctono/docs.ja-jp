---
title: GetHashFromAssemblyFile 関数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f984d44d0a8acb85562a58653dfd2882053a0ce
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799278"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="04b91-102">GetHashFromAssemblyFile 関数</span><span class="sxs-lookup"><span data-stu-id="04b91-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="04b91-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="04b91-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="04b91-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="04b91-104">This function has been deprecated.</span></span> <span data-ttu-id="04b91-105">代わりに[ICLRStrongName:: GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="04b91-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04b91-106">構文</span><span class="sxs-lookup"><span data-stu-id="04b91-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04b91-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04b91-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="04b91-108">からハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="04b91-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="04b91-109">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="04b91-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="04b91-110">既定のハッシュアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="04b91-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="04b91-111">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="04b91-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="04b91-112">から要求された最大`pbHash`サイズ。</span><span class="sxs-lookup"><span data-stu-id="04b91-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="04b91-113">入出力の`pbHash`返されたサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="04b91-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04b91-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="04b91-114">Requirements</span></span>  
 <span data-ttu-id="04b91-115">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04b91-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04b91-116">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="04b91-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="04b91-117">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="04b91-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04b91-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04b91-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b91-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="04b91-119">See also</span></span>

- [<span data-ttu-id="04b91-120">GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="04b91-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="04b91-121">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="04b91-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="04b91-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04b91-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
