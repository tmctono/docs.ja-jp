---
title: ISOSDacInterface インターフェイス
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420969"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="18bd4-102">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18bd4-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="18bd4-103">からデータにアクセスするためのヘルパーメソッドを提供 `SOS` します。</span><span class="sxs-lookup"><span data-stu-id="18bd4-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="18bd4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="18bd4-104">Methods</span></span>

| <span data-ttu-id="18bd4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="18bd4-105">Method</span></span>                                                                                                               | <span data-ttu-id="18bd4-106">説明</span><span class="sxs-lookup"><span data-stu-id="18bd4-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="18bd4-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="18bd4-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="18bd4-108">指定された MethodDesc ポインターのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="18bd4-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="18bd4-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="18bd4-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="18bd4-110">指定されたネイティブ命令アドレスを格納しているメソッドに対応する MethodDesc のポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="18bd4-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="18bd4-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="18bd4-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="18bd4-112">指定したアドレスに読み込まれたモジュールに対応するデータをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="18bd4-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="18bd4-113">解説</span><span class="sxs-lookup"><span data-stu-id="18bd4-113">Remarks</span></span>

<span data-ttu-id="18bd4-114">このインターフェイスはランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="18bd4-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="18bd4-115">ただし、これは、 `IUnknown` `436f00f2-b42a-4b9f-870c-e73db66ae930` 通常の com 機構を通じて取得できる GUID を使用してから派生する com インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="18bd4-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="18bd4-116">要件</span><span class="sxs-lookup"><span data-stu-id="18bd4-116">Requirements</span></span>

<span data-ttu-id="18bd4-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18bd4-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="18bd4-118">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="18bd4-118">**Header:** None</span></span>  
<span data-ttu-id="18bd4-119">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="18bd4-119">**Library:** None</span></span>  
<span data-ttu-id="18bd4-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="18bd4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="18bd4-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="18bd4-121">See also</span></span>

- [<span data-ttu-id="18bd4-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="18bd4-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="18bd4-123">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="18bd4-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
