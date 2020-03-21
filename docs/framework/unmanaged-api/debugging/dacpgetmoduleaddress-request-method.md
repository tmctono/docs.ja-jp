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
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179208"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="8e421-102">メソッドを要求します。</span><span class="sxs-lookup"><span data-stu-id="8e421-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="8e421-103">指定されたランタイム構造体から構造体を設定する要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e421-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8e421-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e421-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="8e421-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e421-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="8e421-106">[in]シード データ モジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8e421-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e421-107">解説</span><span class="sxs-lookup"><span data-stu-id="8e421-107">Remarks</span></span>

<span data-ttu-id="8e421-108">この構造体はランタイム内に存在し、ヘッダーやライブラリ ファイルを通じて公開されません。</span><span class="sxs-lookup"><span data-stu-id="8e421-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8e421-109">これを使用するには、実装を模倣するのが最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="8e421-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="8e421-110">次のパラメーターを使用して、`Request`パラメーターのメソッド`IXCLRDataModule*`を呼び出した結果取得した値を返します。`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="8e421-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="8e421-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e421-111">Requirements</span></span>

<span data-ttu-id="8e421-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e421-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8e421-113">**ヘッダー:** なし**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="8e421-113">**Header:** None **Library:** None</span></span>  
<span data-ttu-id="8e421-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8e421-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8e421-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e421-115">See also</span></span>

- [<span data-ttu-id="8e421-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="8e421-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="8e421-117">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e421-117">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
