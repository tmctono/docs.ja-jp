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
ms.openlocfilehash: 23b567e4119578fba2f8cd4ba47f66dcf56a3878
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496847"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="4934a-102">IXCLRDataProcess::EnumMethodInstanceByAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="4934a-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="4934a-103">このプロセスがアドレス オフセットから始まるのメソッドのインスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="4934a-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4934a-104">構文</span><span class="sxs-lookup"><span data-stu-id="4934a-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="4934a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4934a-105">Parameters</span></span>

`handle`\
<span data-ttu-id="4934a-106">[in]メソッド インスタンスを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="4934a-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="4934a-107">[out]列挙メソッドのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="4934a-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="4934a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4934a-108">Remarks</span></span>

<span data-ttu-id="4934a-109">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、仮想メソッド テーブルの 28 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4934a-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4934a-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4934a-110">Requirements</span></span>

<span data-ttu-id="4934a-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4934a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="4934a-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="4934a-112">**Header:** None</span></span>   
<span data-ttu-id="4934a-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="4934a-113">**Library:** None</span></span>   
<span data-ttu-id="4934a-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4934a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="4934a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4934a-115">See also</span></span>
- [<span data-ttu-id="4934a-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="4934a-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="4934a-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4934a-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="4934a-118">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4934a-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
