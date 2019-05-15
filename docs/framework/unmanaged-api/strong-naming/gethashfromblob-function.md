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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba049723710b378a90d17c67735a05e8a09d05d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636857"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="cc86f-102">GetHashFromBlob 関数</span><span class="sxs-lookup"><span data-stu-id="cc86f-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="cc86f-103">指定したハッシュ アルゴリズムを使用して、指定したメモリ アドレスにあるアセンブリのハッシュが取得されます。</span><span class="sxs-lookup"><span data-stu-id="cc86f-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="cc86f-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="cc86f-104">This function has been deprecated.</span></span> <span data-ttu-id="cc86f-105">使用して、 [iclrstrongname::gethashfromblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="cc86f-105">Use the [ICLRStrongName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc86f-106">構文</span><span class="sxs-lookup"><span data-stu-id="cc86f-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="cc86f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cc86f-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="cc86f-108">[in]ハッシュされるメモリ ブロックのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cc86f-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="cc86f-109">[in]メモリ ブロックの長さ、(バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="cc86f-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="cc86f-110">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="cc86f-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cc86f-111">既定のアルゴリズムに 0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc86f-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="cc86f-112">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="cc86f-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="cc86f-113">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="cc86f-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="cc86f-114">[out]サイズ (バイト単位)、返された`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="cc86f-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc86f-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="cc86f-115">Requirements</span></span>

<span data-ttu-id="cc86f-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc86f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="cc86f-117">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cc86f-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="cc86f-118">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cc86f-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="cc86f-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc86f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cc86f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc86f-120">See also</span></span>

- [<span data-ttu-id="cc86f-121">GetHashFromBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="cc86f-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="cc86f-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc86f-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
