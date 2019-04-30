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
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948806"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="f610d-102">ICorDebugProcess4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f610d-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="f610d-103">プロセス実行の制御外のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="f610d-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="f610d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f610d-104">Methods</span></span>

| <span data-ttu-id="f610d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f610d-105">Method</span></span>                                                                 | <span data-ttu-id="f610d-106">説明</span><span class="sxs-lookup"><span data-stu-id="f610d-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="f610d-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="f610d-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="f610d-108">デバッガーをプロセスの出力がデバッグ対象の実行を続行は ICorDebug パイプラインに通知します。</span><span class="sxs-lookup"><span data-stu-id="f610d-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f610d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f610d-109">Remarks</span></span>

<span data-ttu-id="f610d-110">このインターフェイスは、ランタイム内に収めるを任意のヘッダーまたはライブラリ ファイルを通じて公開されていません。</span><span class="sxs-lookup"><span data-stu-id="f610d-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="f610d-111">ただし、これは COM インターフェイスから派生した`IUnknown`GUID を持つ`E930C679-78AF-4953-8AB7-B0AABF0F9F80`を通常の COM メカニズムを通じて取得できます。</span><span class="sxs-lookup"><span data-stu-id="f610d-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="f610d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="f610d-112">Requirements</span></span>

<span data-ttu-id="f610d-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f610d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f610d-114">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="f610d-114">**Header:** None</span></span>

<span data-ttu-id="f610d-115">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="f610d-115">**Library:** None</span></span>

<span data-ttu-id="f610d-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f610d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f610d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f610d-117">See also</span></span>

- [<span data-ttu-id="f610d-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f610d-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f610d-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f610d-119">Debugging</span></span>](index.md)
