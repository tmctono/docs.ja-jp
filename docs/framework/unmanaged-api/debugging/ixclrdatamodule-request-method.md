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
ms.openlocfilehash: a02a60668ae6caaad1940395822758331b93f550
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119796"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="be12d-102">IXCLRDataModule::Request メソッド</span><span class="sxs-lookup"><span data-stu-id="be12d-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="be12d-103">要求をモジュールのデータで指定されたバッファーを設定します。</span><span class="sxs-lookup"><span data-stu-id="be12d-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="be12d-104">構文</span><span class="sxs-lookup"><span data-stu-id="be12d-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="be12d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be12d-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="be12d-106">[in]要求の種類を送信します。</span><span class="sxs-lookup"><span data-stu-id="be12d-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="be12d-107">[in] で渡される入力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="be12d-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="be12d-108">[in、size_is(inBufferSize)]要求で送信される生データのバッファー ポインター。</span><span class="sxs-lookup"><span data-stu-id="be12d-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="be12d-109">[in]出力バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="be12d-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="be12d-110">[out, size_is(outBufferSize)]要求の応答を格納するために使用するバッファーのポインター。</span><span class="sxs-lookup"><span data-stu-id="be12d-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="be12d-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="be12d-111">Remarks</span></span>

<span data-ttu-id="be12d-112">指定されたメソッドは、`IXCLRDataModule`インターフェイスし、仮想メソッド テーブルの 36th スロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="be12d-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="be12d-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="be12d-113">Requirements</span></span>

<span data-ttu-id="be12d-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be12d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="be12d-115">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="be12d-115">**Header:** None</span></span>   
<span data-ttu-id="be12d-116">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="be12d-116">**Library:** None</span></span>  
**<span data-ttu-id="be12d-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="be12d-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="be12d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="be12d-118">See also</span></span>

- [<span data-ttu-id="be12d-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="be12d-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="be12d-120">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be12d-120">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)