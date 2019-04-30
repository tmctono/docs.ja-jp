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
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000533"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="cccc1-102">GetHashFromBlob 関数</span><span class="sxs-lookup"><span data-stu-id="cccc1-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="cccc1-103">指定したハッシュ アルゴリズムを使用して、指定したメモリ アドレスにあるアセンブリのハッシュが取得されます。</span><span class="sxs-lookup"><span data-stu-id="cccc1-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="cccc1-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="cccc1-104">This function has been deprecated.</span></span> <span data-ttu-id="cccc1-105">使用して、 [iclrstrongname::gethashfromblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="cccc1-105">Use the [ICLRStrongName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="cccc1-106">構文</span><span class="sxs-lookup"><span data-stu-id="cccc1-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="cccc1-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cccc1-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="cccc1-108">[in]ハッシュされるメモリ ブロックのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cccc1-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="cccc1-109">[in]メモリ ブロックの長さ、(バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="cccc1-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="cccc1-110">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="cccc1-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cccc1-111">既定のアルゴリズムに 0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="cccc1-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="cccc1-112">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="cccc1-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="cccc1-113">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="cccc1-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="cccc1-114">[out]サイズ (バイト単位)、返された`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="cccc1-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="cccc1-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="cccc1-115">Requirements</span></span>

<span data-ttu-id="cccc1-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cccc1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="cccc1-117">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cccc1-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="cccc1-118">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cccc1-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="cccc1-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cccc1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cccc1-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="cccc1-120">See also</span></span>

- [<span data-ttu-id="cccc1-121">GetHashFromBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="cccc1-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="cccc1-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cccc1-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)