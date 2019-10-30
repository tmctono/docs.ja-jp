---
title: ISymUnmanagedWriter4 インターフェイス
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: a656777461c50b5a1593917278eb54abda982dc2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134562"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="ec59d-102">ISymUnmanagedWriter4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec59d-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="ec59d-103">ISymUnmanagedWriter4 インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ec59d-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec59d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ec59d-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="ec59d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ec59d-105">Methods</span></span>  
 <span data-ttu-id="ec59d-106">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec59d-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="ec59d-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="ec59d-107">Method</span></span>|<span data-ttu-id="ec59d-108">説明</span><span class="sxs-lookup"><span data-stu-id="ec59d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec59d-109">GetDebugInfoWithPadding メソッド</span><span class="sxs-lookup"><span data-stu-id="ec59d-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="ec59d-110">[GetDebugInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)と同じように機能します。ただし、文字列データの固定サイズを `MAX_PATH`にするために、終端の null 文字の後にパス文字列がゼロで埋め込まれる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="ec59d-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="ec59d-111">埋め込みは、パス文字列の長さが `MAX_PATH`未満の場合にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="ec59d-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="ec59d-112">これにより、PE ファイルを区別するツールを簡単に記述できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ec59d-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec59d-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="ec59d-113">Requirements</span></span>  
 <span data-ttu-id="ec59d-114">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="ec59d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec59d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec59d-115">See also</span></span>

- [<span data-ttu-id="ec59d-116">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec59d-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ec59d-117">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec59d-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
