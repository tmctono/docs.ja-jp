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
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790406"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="c3deb-102">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3deb-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="c3deb-103">メソッドインスタンスに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3deb-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="c3deb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c3deb-104">Methods</span></span>

| <span data-ttu-id="c3deb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c3deb-105">Method</span></span>                                                                                                                  | <span data-ttu-id="c3deb-106">説明</span><span class="sxs-lookup"><span data-stu-id="c3deb-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="c3deb-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="c3deb-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="c3deb-108">マッピング情報をアドレス付けする IL を取得します。</span><span class="sxs-lookup"><span data-stu-id="c3deb-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="c3deb-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="c3deb-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="c3deb-110">メソッドに対して使用可能なすべてのエントリポイントのネイティブコンパイルを行うための最も代表的なエントリポイントアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3deb-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c3deb-111">コメント</span><span class="sxs-lookup"><span data-stu-id="c3deb-111">Remarks</span></span>

<span data-ttu-id="c3deb-112">このインターフェイスはランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c3deb-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c3deb-113">ただし、これは、通常の COM 機構を通じて取得できる GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` を `IUnknown` から派生する COM インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="c3deb-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3deb-114">要件</span><span class="sxs-lookup"><span data-stu-id="c3deb-114">Requirements</span></span>

<span data-ttu-id="c3deb-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3deb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c3deb-116">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="c3deb-116">**Header:** None</span></span>  
<span data-ttu-id="c3deb-117">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="c3deb-117">**Library:** None</span></span>  
<span data-ttu-id="c3deb-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3deb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c3deb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3deb-119">See also</span></span>

- [<span data-ttu-id="c3deb-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c3deb-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="c3deb-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3deb-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
