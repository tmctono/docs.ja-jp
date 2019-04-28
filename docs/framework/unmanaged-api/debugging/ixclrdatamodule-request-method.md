---
title: IXCLRDataModule::Request メソッド
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
ms.openlocfilehash: 755063ca6da29a2e4733dd653306192ac0434ec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775454"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="724c4-102">IXCLRDataModule::Request メソッド</span><span class="sxs-lookup"><span data-stu-id="724c4-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="724c4-103">要求をモジュールのデータで指定されたバッファーを設定します。</span><span class="sxs-lookup"><span data-stu-id="724c4-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="724c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="724c4-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="724c4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="724c4-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="724c4-106">[in]要求の種類を送信します。</span><span class="sxs-lookup"><span data-stu-id="724c4-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="724c4-107">[in] で渡される入力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="724c4-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="724c4-108">[in、size_is(inBufferSize)]要求で送信される生データのバッファー ポインター。</span><span class="sxs-lookup"><span data-stu-id="724c4-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="724c4-109">[in]出力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="724c4-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="724c4-110">[out, size_is(outBufferSize)]要求の応答を格納するために使用するバッファーのポインター。</span><span class="sxs-lookup"><span data-stu-id="724c4-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="724c4-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="724c4-111">Remarks</span></span>

<span data-ttu-id="724c4-112">指定されたメソッドは、`IXCLRDataModule`インターフェイスし、仮想メソッド テーブルの 36th スロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="724c4-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="724c4-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="724c4-113">Requirements</span></span>

<span data-ttu-id="724c4-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="724c4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="724c4-115">**ヘッダー:** None**ライブラリ。** None **.NET Framework のバージョン。** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="724c4-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="724c4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="724c4-116">See also</span></span>

- [<span data-ttu-id="724c4-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="724c4-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="724c4-118">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="724c4-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)