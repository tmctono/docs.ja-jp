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
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860844"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="64d58-102">DacpGetModuleAddress::Request メソッド</span><span class="sxs-lookup"><span data-stu-id="64d58-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="64d58-103">指定されたランタイム構造体を構造体に設定する要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="64d58-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="64d58-104">構文</span><span class="sxs-lookup"><span data-stu-id="64d58-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="64d58-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="64d58-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="64d58-106">からシードデータモジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="64d58-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="64d58-107">解説</span><span class="sxs-lookup"><span data-stu-id="64d58-107">Remarks</span></span>

<span data-ttu-id="64d58-108">この構造体はランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="64d58-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="64d58-109">これを使用する最も簡単な方法は、実装を模倣することです。</span><span class="sxs-lookup"><span data-stu-id="64d58-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="64d58-110">次のパラメーターを使用して`Request` 、 `IXCLRDataModule*`パラメーターのメソッドの呼び出しから取得した値を返します。`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="64d58-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="64d58-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="64d58-111">Requirements</span></span>

<span data-ttu-id="64d58-112">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64d58-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="64d58-113">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="64d58-113">**Header:** None\</span></span>
<span data-ttu-id="64d58-114">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="64d58-114">**Library:** None\</span></span>
<span data-ttu-id="64d58-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="64d58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="64d58-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="64d58-116">See also</span></span>

- [<span data-ttu-id="64d58-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="64d58-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="64d58-118">DacpGetModuleAddress 構造体</span><span class="sxs-lookup"><span data-stu-id="64d58-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
