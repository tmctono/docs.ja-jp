---
title: IXCLRDataMethodInstance インターフェイス
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0b1c982b25af9edea76a038b4314b4bd608f07df
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420891"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="900a7-102">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="900a7-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="900a7-103">メソッドインスタンスに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="900a7-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="900a7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="900a7-104">Methods</span></span>

| <span data-ttu-id="900a7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="900a7-105">Method</span></span>                                                                                                                  | <span data-ttu-id="900a7-106">説明</span><span class="sxs-lookup"><span data-stu-id="900a7-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="900a7-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="900a7-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="900a7-108">マッピング情報をアドレス付けする IL を取得します。</span><span class="sxs-lookup"><span data-stu-id="900a7-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="900a7-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="900a7-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="900a7-110">メソッドに対して使用可能なすべてのエントリポイントのネイティブコンパイルを行うための最も代表的なエントリポイントアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="900a7-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="900a7-111">解説</span><span class="sxs-lookup"><span data-stu-id="900a7-111">Remarks</span></span>

<span data-ttu-id="900a7-112">このインターフェイスはランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="900a7-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="900a7-113">ただし、これは、 `IUnknown` `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` 通常の com 機構を通じて取得できる GUID を使用してから派生する com インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="900a7-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="900a7-114">要件</span><span class="sxs-lookup"><span data-stu-id="900a7-114">Requirements</span></span>

<span data-ttu-id="900a7-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="900a7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="900a7-116">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="900a7-116">**Header:** None</span></span>  
<span data-ttu-id="900a7-117">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="900a7-117">**Library:** None</span></span>  
<span data-ttu-id="900a7-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="900a7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="900a7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="900a7-119">See also</span></span>

- [<span data-ttu-id="900a7-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="900a7-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="900a7-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="900a7-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
