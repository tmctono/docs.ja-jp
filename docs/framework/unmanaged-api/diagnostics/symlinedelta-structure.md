---
title: SYMLINEDELTA 構造体
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: a1e83e4b8cb6603029f3b42b1a3b9ba4810c9039
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438016"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="5a4ab-102">SYMLINEDELTA 構造体</span><span class="sxs-lookup"><span data-stu-id="5a4ab-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="5a4ab-103">編集の結果として移動されたメソッドについて、シンボルハンドラーに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5a4ab-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a4ab-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a4ab-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="5a4ab-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5a4ab-105">Members</span></span>  
  
|<span data-ttu-id="5a4ab-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5a4ab-106">Member</span></span>|<span data-ttu-id="5a4ab-107">説明</span><span class="sxs-lookup"><span data-stu-id="5a4ab-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="5a4ab-108">メソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="5a4ab-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="5a4ab-109">メソッドが移動された行の数。</span><span class="sxs-lookup"><span data-stu-id="5a4ab-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a4ab-110">要件</span><span class="sxs-lookup"><span data-stu-id="5a4ab-110">Requirements</span></span>  
 <span data-ttu-id="5a4ab-111">**ヘッダー:** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="5a4ab-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4ab-112">参照</span><span class="sxs-lookup"><span data-stu-id="5a4ab-112">See also</span></span>

- [<span data-ttu-id="5a4ab-113">シンボル ストア診断構造体</span><span class="sxs-lookup"><span data-stu-id="5a4ab-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
