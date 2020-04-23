---
title: メソッドを要求します。
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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102908"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="52496-102">メソッドを要求します。</span><span class="sxs-lookup"><span data-stu-id="52496-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="52496-103">指定されたランタイム構造体から構造体を設定する要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="52496-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="52496-104">構文</span><span class="sxs-lookup"><span data-stu-id="52496-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="52496-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="52496-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="52496-106">[in]シード データ モジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="52496-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="52496-107">解説</span><span class="sxs-lookup"><span data-stu-id="52496-107">Remarks</span></span>

<span data-ttu-id="52496-108">この構造体はランタイム内に存在し、ヘッダーやライブラリ ファイルを通じて公開されません。</span><span class="sxs-lookup"><span data-stu-id="52496-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="52496-109">これを使用するには、実装を模倣するのが最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="52496-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="52496-110">次のパラメーターを使用して、`Request`パラメーターのメソッド`IXCLRDataModule*`を呼び出した結果取得した値を返します。`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="52496-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="52496-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="52496-111">Requirements</span></span>

<span data-ttu-id="52496-112">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52496-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md)</span></span>\
<span data-ttu-id="52496-113">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="52496-113">**Header:** None</span></span>\
<span data-ttu-id="52496-114">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="52496-114">**Library:** None</span></span>\
<span data-ttu-id="52496-115">**.NET フレームワークのバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="52496-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="52496-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="52496-116">See also</span></span>

- [<span data-ttu-id="52496-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="52496-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="52496-118">構造体</span><span class="sxs-lookup"><span data-stu-id="52496-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
