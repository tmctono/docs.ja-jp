---
title: IXCLRDataProcess::EnumMethodInstanceByAddress メソッド
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a51c709b0b331127b74d98c4dc42e2772fd7f2db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775467"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="405eb-102">IXCLRDataProcess::EnumMethodInstanceByAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="405eb-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="405eb-103">このプロセスがアドレス オフセットから始まるのメソッドのインスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="405eb-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="405eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="405eb-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="405eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="405eb-105">Parameters</span></span>

`handle`\
<span data-ttu-id="405eb-106">[in]メソッド インスタンスを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="405eb-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="405eb-107">[out]列挙メソッドのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="405eb-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="405eb-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="405eb-108">Remarks</span></span>

<span data-ttu-id="405eb-109">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、仮想メソッド テーブルの 28 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="405eb-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="405eb-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="405eb-110">Requirements</span></span>

<span data-ttu-id="405eb-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="405eb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="405eb-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="405eb-112">**Header:** None</span></span>   
<span data-ttu-id="405eb-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="405eb-113">**Library:** None</span></span>   
<span data-ttu-id="405eb-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="405eb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="405eb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="405eb-115">See also</span></span>

- [<span data-ttu-id="405eb-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="405eb-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="405eb-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="405eb-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="405eb-118">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="405eb-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
