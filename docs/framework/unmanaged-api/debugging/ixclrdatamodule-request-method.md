---
title: 'IXCLRDataModule:: Request メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3c18fc5c947cbb89fc4e9aed60d3cedcbe22d749
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420813"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="c1974-102">IXCLRDataModule:: Request メソッド</span><span class="sxs-lookup"><span data-stu-id="c1974-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="c1974-103">モジュールのデータで指定されたバッファーへの読み込みを要求します。</span><span class="sxs-lookup"><span data-stu-id="c1974-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c1974-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1974-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="c1974-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1974-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="c1974-106">から送信される要求の種類。</span><span class="sxs-lookup"><span data-stu-id="c1974-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="c1974-107">[in] 渡される入力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="c1974-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="c1974-108">[in、size_is (inBufferSize)]要求で送信される生データのバッファーポインター。</span><span class="sxs-lookup"><span data-stu-id="c1974-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="c1974-109">から出力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="c1974-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="c1974-110">[out、size_is (outBufferSize)]要求応答を格納するために使用するバッファーポインター。</span><span class="sxs-lookup"><span data-stu-id="c1974-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1974-111">解説</span><span class="sxs-lookup"><span data-stu-id="c1974-111">Remarks</span></span>

<span data-ttu-id="c1974-112">指定されたメソッドはインターフェイスの一部で `IXCLRDataModule` あり、仮想メソッドテーブルの37th スロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="c1974-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 37th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="c1974-113">要件</span><span class="sxs-lookup"><span data-stu-id="c1974-113">Requirements</span></span>

<span data-ttu-id="c1974-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1974-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="c1974-115">**ヘッダー:** None **Library:** None **.NET Framework バージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c1974-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c1974-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1974-116">See also</span></span>

- [<span data-ttu-id="c1974-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c1974-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="c1974-118">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1974-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
