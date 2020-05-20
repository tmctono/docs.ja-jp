---
title: IXCLRDataModule インターフェイス
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3c2bc771c0a131329b9403c99a33ca7b79023771
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420852"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="404a4-102">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="404a4-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="404a4-103">読み込まれたモジュールに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="404a4-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="404a4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="404a4-104">Methods</span></span>

| <span data-ttu-id="404a4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="404a4-105">Method</span></span>                                                                                                                                | <span data-ttu-id="404a4-106">説明</span><span class="sxs-lookup"><span data-stu-id="404a4-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="404a4-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="404a4-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="404a4-108">指定されたメタデータトークンに対応するメソッド定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="404a4-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="404a4-109">Request</span><span class="sxs-lookup"><span data-stu-id="404a4-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="404a4-110">モジュールのデータで指定されたバッファーへの読み込みを要求します。</span><span class="sxs-lookup"><span data-stu-id="404a4-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="404a4-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="404a4-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="404a4-112">モジュールのバージョン ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="404a4-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="404a4-113">解説</span><span class="sxs-lookup"><span data-stu-id="404a4-113">Remarks</span></span>

<span data-ttu-id="404a4-114">このインターフェイスはランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="404a4-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="404a4-115">ただし、これは、 `IUnknown` `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` 通常の com 機構を通じて取得できる GUID を使用してから派生する com インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="404a4-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="404a4-116">要件</span><span class="sxs-lookup"><span data-stu-id="404a4-116">Requirements</span></span>

<span data-ttu-id="404a4-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="404a4-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="404a4-118">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="404a4-118">**Header:** None</span></span>  
<span data-ttu-id="404a4-119">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="404a4-119">**Library:** None</span></span>  
<span data-ttu-id="404a4-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="404a4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="404a4-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="404a4-121">See also</span></span>

- [<span data-ttu-id="404a4-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="404a4-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="404a4-123">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="404a4-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
