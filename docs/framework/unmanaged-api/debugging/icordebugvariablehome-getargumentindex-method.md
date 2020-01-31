---
title: 'いい変数 Home:: GetArgumentIndex メソッド'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 12d4e63480f03bfad613f30362ddaeaf12b57a88
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791047"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="438bc-102">いい変数 Home:: GetArgumentIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="438bc-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="438bc-103">関数の引数のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="438bc-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="438bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="438bc-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="438bc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="438bc-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="438bc-106">入出力引数インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="438bc-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="438bc-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="438bc-107">Return Value</span></span>

<span data-ttu-id="438bc-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="438bc-108">The method returns the following values.</span></span>

|<span data-ttu-id="438bc-109">Value</span><span class="sxs-lookup"><span data-stu-id="438bc-109">Value</span></span>|<span data-ttu-id="438bc-110">説明</span><span class="sxs-lookup"><span data-stu-id="438bc-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="438bc-111">メソッド呼び出しによって有効な引数インデックスが返されました。</span><span class="sxs-lookup"><span data-stu-id="438bc-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="438bc-112">現在の[ページ](icordebugvariablehome-interface.md)は、ローカル変数を表します。</span><span class="sxs-lookup"><span data-stu-id="438bc-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="438bc-113">コメント</span><span class="sxs-lookup"><span data-stu-id="438bc-113">Remarks</span></span>

<span data-ttu-id="438bc-114">引数インデックスは、この引数のメタデータを取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="438bc-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="438bc-115">要件</span><span class="sxs-lookup"><span data-stu-id="438bc-115">Requirements</span></span>

<span data-ttu-id="438bc-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="438bc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="438bc-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="438bc-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="438bc-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="438bc-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="438bc-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="438bc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="438bc-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="438bc-120">See also</span></span>

- [<span data-ttu-id="438bc-121">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="438bc-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
