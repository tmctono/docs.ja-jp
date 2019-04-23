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
ms.openlocfilehash: f62cbdc4b3e73f0c27492f7ed20b35378654d399
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152959"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="37139-102">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37139-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="37139-103">メソッド インスタンスの情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="37139-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="37139-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="37139-104">Methods</span></span>

| <span data-ttu-id="37139-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="37139-105">Method</span></span>                                                                                                                  | <span data-ttu-id="37139-106">説明</span><span class="sxs-lookup"><span data-stu-id="37139-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="37139-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="37139-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="37139-108">アドレスのマッピング情報の IL を取得します。</span><span class="sxs-lookup"><span data-stu-id="37139-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="37139-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="37139-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="37139-110">メソッドのエントリ ポイントは、すべてのネイティブ コンパイルの最も代表的なエントリ ポイントのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="37139-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="37139-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="37139-111">Remarks</span></span>

<span data-ttu-id="37139-112">このインターフェイスは、ランタイム内に収めるを任意のヘッダーまたはライブラリ ファイルでは公開されません。</span><span class="sxs-lookup"><span data-stu-id="37139-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="37139-113">ただし、これは COM インターフェイスから派生した`IUnknown`GUID を持つ`ECD73800-22CA-4b0d-AB55-E9BA7E6318A5`を通常の COM メカニズムを通じて取得できます。</span><span class="sxs-lookup"><span data-stu-id="37139-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="37139-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="37139-114">Requirements</span></span>

<span data-ttu-id="37139-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="37139-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="37139-116">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="37139-116">**Header:** None</span></span>  
<span data-ttu-id="37139-117">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="37139-117">**Library:** None</span></span>  
<span data-ttu-id="37139-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="37139-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="37139-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="37139-119">See also</span></span>

- [<span data-ttu-id="37139-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="37139-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="37139-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37139-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
