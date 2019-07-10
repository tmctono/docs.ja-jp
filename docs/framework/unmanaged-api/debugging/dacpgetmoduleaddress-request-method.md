---
title: DacpGetModuleAddress::Request メソッド
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 07ad83da2bc608e3c5925664a68eec4a548860e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739223"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="87ac4-102">DacpGetModuleAddress::Request メソッド</span><span class="sxs-lookup"><span data-stu-id="87ac4-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="87ac4-103">指定したランタイムの構造体から構造の作成要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="87ac4-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="87ac4-104">構文</span><span class="sxs-lookup"><span data-stu-id="87ac4-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="87ac4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87ac4-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="87ac4-106">[in]シード データ モジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="87ac4-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="87ac4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="87ac4-107">Remarks</span></span>

<span data-ttu-id="87ac4-108">この構造は、ランタイム内に収めるし、任意のヘッダーまたはライブラリ ファイルでは公開されません。</span><span class="sxs-lookup"><span data-stu-id="87ac4-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="87ac4-109">これを使用するには、最も簡単な方法は、実装を模倣するためには。</span><span class="sxs-lookup"><span data-stu-id="87ac4-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="87ac4-110">呼び出し元から取得した値を返す、`Request`メソッドを`IXCLRDataModule*`パラメーターは次のパラメーター。 `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="87ac4-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="87ac4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="87ac4-111">Requirements</span></span>

<span data-ttu-id="87ac4-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87ac4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="87ac4-113">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="87ac4-113">**Header:** None</span></span>     
<span data-ttu-id="87ac4-114">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="87ac4-114">**Library:** None</span></span>  
<span data-ttu-id="87ac4-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87ac4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="87ac4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="87ac4-116">See also</span></span>

- [<span data-ttu-id="87ac4-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="87ac4-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="87ac4-118">DacpGetModuleAddress インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87ac4-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
