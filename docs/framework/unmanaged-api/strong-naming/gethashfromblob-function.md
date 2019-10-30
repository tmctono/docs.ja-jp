---
title: GetHashFromBlob 関数
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140714"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="6d339-102">GetHashFromBlob 関数</span><span class="sxs-lookup"><span data-stu-id="6d339-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="6d339-103">指定したハッシュ アルゴリズムを使用して、指定したメモリ アドレスにあるアセンブリのハッシュが取得されます。</span><span class="sxs-lookup"><span data-stu-id="6d339-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="6d339-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="6d339-104">This function has been deprecated.</span></span> <span data-ttu-id="6d339-105">代わりに[ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6d339-105">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d339-106">構文</span><span class="sxs-lookup"><span data-stu-id="6d339-106">Syntax</span></span>

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a><span data-ttu-id="6d339-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d339-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="6d339-108">からハッシュされるメモリブロックのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6d339-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="6d339-109">からメモリブロックの長さ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6d339-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="6d339-110">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="6d339-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="6d339-111">既定のアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d339-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="6d339-112">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="6d339-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="6d339-113">から要求された `pbHash`の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="6d339-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="6d339-114">入出力返された `pbHash`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6d339-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="6d339-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="6d339-115">Requirements</span></span>

<span data-ttu-id="6d339-116">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d339-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6d339-117">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="6d339-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="6d339-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6d339-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="6d339-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d339-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6d339-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d339-120">See also</span></span>

- [<span data-ttu-id="6d339-121">GetHashFromBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="6d339-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="6d339-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d339-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
