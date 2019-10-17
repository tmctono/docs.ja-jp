---
title: ICorDebugCode2::GetCodeChunks メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d64773aa0d35f2e97232576d145dfcba624812ec
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395527"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="0f806-102">ICorDebugCode2::GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="0f806-102">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="0f806-103">このコード オブジェクトを構成しているコード チャンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="0f806-103">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f806-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f806-104">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="0f806-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f806-105">Parameters</span></span>

`cbufSize`  
<span data-ttu-id="0f806-106">から@No__t-0 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="0f806-106">[in] Size of the `chunks` array.</span></span>

`pcnumChunks`  
<span data-ttu-id="0f806-107">入出力@No__t-0 配列で返されたチャンクの数。</span><span class="sxs-lookup"><span data-stu-id="0f806-107">[out] The number of chunks returned in the `chunks` array.</span></span>

`chunks`  
<span data-ttu-id="0f806-108">入出力"CodeChunkInfo" 構造体の配列。それぞれが1つのコードチャンクを表します。</span><span class="sxs-lookup"><span data-stu-id="0f806-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="0f806-109">@No__t-0 の値が0の場合、このパラメーターには null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0f806-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f806-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f806-110">Remarks</span></span>

<span data-ttu-id="0f806-111">コードチャンクは重複しません。コードチャンクは、「[コード:: GetCode](icordebugcode-getcode-method.md)」によって連結された順序に従います。</span><span class="sxs-lookup"><span data-stu-id="0f806-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="0f806-112">.NET Framework バージョン2.0 の Microsoft 中間言語 (MSIL) コードオブジェクトは、1つのコードチャンクを構成します。</span><span class="sxs-lookup"><span data-stu-id="0f806-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f806-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="0f806-113">Requirements</span></span>

<span data-ttu-id="0f806-114">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f806-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0f806-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f806-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="0f806-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f806-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0f806-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f806-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
