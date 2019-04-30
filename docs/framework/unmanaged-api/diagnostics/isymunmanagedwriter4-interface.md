---
title: ISymUnmanagedWriter4 インターフェイス
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5732cc08512df25a14cc8ea9dcaa03c56207dde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962334"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="f7cf9-102">ISymUnmanagedWriter4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7cf9-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="f7cf9-103">ISymUnmanagedWriter4 インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="f7cf9-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7cf9-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7cf9-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="f7cf9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f7cf9-105">Methods</span></span>  
 <span data-ttu-id="f7cf9-106">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7cf9-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="f7cf9-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="f7cf9-107">Method</span></span>|<span data-ttu-id="f7cf9-108">説明</span><span class="sxs-lookup"><span data-stu-id="f7cf9-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7cf9-109">GetDebugInfoWithPadding メソッド</span><span class="sxs-lookup"><span data-stu-id="f7cf9-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="f7cf9-110">機能と同じ[GetDebugInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)パス文字列は、文字列データの固定サイズの終端の null 文字の後に続くゼロで埋められますことを除いて`MAX_PATH`します。</span><span class="sxs-lookup"><span data-stu-id="f7cf9-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="f7cf9-111">自体のパス文字列の長さがある場合、余白が指定されたのみより小さい`MAX_PATH`します。</span><span class="sxs-lookup"><span data-stu-id="f7cf9-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="f7cf9-112">これにより、その差分 PE ファイル ツールを記述しやすくします。</span><span class="sxs-lookup"><span data-stu-id="f7cf9-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7cf9-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7cf9-113">Requirements</span></span>  
 <span data-ttu-id="f7cf9-114">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7cf9-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7cf9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7cf9-115">See also</span></span>

- [<span data-ttu-id="f7cf9-116">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7cf9-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="f7cf9-117">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7cf9-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
