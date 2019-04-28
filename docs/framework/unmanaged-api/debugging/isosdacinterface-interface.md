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
ms.openlocfilehash: ccaf479fc4fb90007b4999e95ee03bdd0529321e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922149"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="cded2-102">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cded2-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="cded2-103">データにアクセスするヘルパー メソッドを提供します。`SOS`します。</span><span class="sxs-lookup"><span data-stu-id="cded2-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="cded2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cded2-104">Methods</span></span>

| <span data-ttu-id="cded2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cded2-105">Method</span></span>                                                                                                               | <span data-ttu-id="cded2-106">説明</span><span class="sxs-lookup"><span data-stu-id="cded2-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="cded2-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="cded2-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="cded2-108">指定した MethodDesc ポインターのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="cded2-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="cded2-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="cded2-109">GetMethodDescPtrFromIP</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="cded2-110">指定されたネイティブ命令のアドレスを含むメソッドに対応する MethodDesc ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="cded2-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="cded2-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="cded2-111">GetModuleData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="cded2-112">指定したアドレスに読み込まれたモジュールに対応するデータをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="cded2-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cded2-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="cded2-113">Remarks</span></span>

<span data-ttu-id="cded2-114">このインターフェイスは、ランタイム内に収めるを任意のヘッダーまたはライブラリ ファイルでは公開されません。</span><span class="sxs-lookup"><span data-stu-id="cded2-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="cded2-115">ただし、これは COM インターフェイスから派生した`IUnknown`GUID を持つ`436f00f2-b42a-4b9f-870c-e73db66ae930`を通常の COM メカニズムを通じて取得できます。</span><span class="sxs-lookup"><span data-stu-id="cded2-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="cded2-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="cded2-116">Requirements</span></span>

<span data-ttu-id="cded2-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cded2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="cded2-118">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="cded2-118">**Header:** None</span></span>  
<span data-ttu-id="cded2-119">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="cded2-119">**Library:** None</span></span>  
<span data-ttu-id="cded2-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cded2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cded2-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="cded2-121">See also</span></span>

- [<span data-ttu-id="cded2-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="cded2-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="cded2-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cded2-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
