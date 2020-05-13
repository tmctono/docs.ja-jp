---
title: ICorDebugProcess4 インターフェイス
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213583"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="95c5f-102">ICorDebugProcess4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95c5f-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="95c5f-103">アウトプロセス実行制御のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="95c5f-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="95c5f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="95c5f-104">Methods</span></span>

| <span data-ttu-id="95c5f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="95c5f-105">Method</span></span>                                                                 | <span data-ttu-id="95c5f-106">説明</span><span class="sxs-lookup"><span data-stu-id="95c5f-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="95c5f-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="95c5f-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="95c5f-108">アウトプロセスデバッガーがデバッグ対象の実行を継続していることを ICorDebug パイプラインに通知します。</span><span class="sxs-lookup"><span data-stu-id="95c5f-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="95c5f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="95c5f-109">Remarks</span></span>

<span data-ttu-id="95c5f-110">このインターフェイスはランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="95c5f-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="95c5f-111">ただし、これは、 `IUnknown` `E930C679-78AF-4953-8AB7-B0AABF0F9F80` 通常の com 機構を通じて取得できる GUID を使用してから派生する com インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="95c5f-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="95c5f-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="95c5f-112">Requirements</span></span>

<span data-ttu-id="95c5f-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c5f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="95c5f-114">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="95c5f-114">**Header:** None</span></span>

<span data-ttu-id="95c5f-115">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="95c5f-115">**Library:** None</span></span>

<span data-ttu-id="95c5f-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95c5f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="95c5f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="95c5f-117">See also</span></span>

- [<span data-ttu-id="95c5f-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="95c5f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="95c5f-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="95c5f-119">Debugging</span></span>](index.md)
