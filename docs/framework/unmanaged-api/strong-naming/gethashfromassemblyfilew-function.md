---
title: GetHashFromAssemblyFileW 関数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4b748370ff1aff042923002ad827a0e39d99963
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799273"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="330de-102">GetHashFromAssemblyFileW 関数</span><span class="sxs-lookup"><span data-stu-id="330de-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="330de-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="330de-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="330de-104">アセンブリファイルへのパスは、Unicode 文字列として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="330de-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="330de-105">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="330de-105">This function has been deprecated.</span></span> <span data-ttu-id="330de-106">代わりに[ICLRStrongName:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="330de-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="330de-107">構文</span><span class="sxs-lookup"><span data-stu-id="330de-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="330de-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="330de-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="330de-109">からハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="330de-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="330de-110">このパラメーターは Unicode 文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="330de-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="330de-111">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="330de-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="330de-112">既定のハッシュアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="330de-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="330de-113">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="330de-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="330de-114">から要求された最大`pbHash`サイズ。</span><span class="sxs-lookup"><span data-stu-id="330de-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="330de-115">入出力の`pbHash`返されたサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="330de-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="330de-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="330de-116">Requirements</span></span>  
 <span data-ttu-id="330de-117">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="330de-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="330de-118">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="330de-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="330de-119">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="330de-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="330de-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="330de-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="330de-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="330de-121">See also</span></span>

- [<span data-ttu-id="330de-122">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="330de-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="330de-123">GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="330de-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="330de-124">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="330de-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
