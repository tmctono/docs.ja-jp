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
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609301"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="c06a3-102">SYMLINEDELTA 構造体</span><span class="sxs-lookup"><span data-stu-id="c06a3-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="c06a3-103">編集の結果として移動されたメソッドについて、シンボルハンドラーに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c06a3-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c06a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="c06a3-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="c06a3-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c06a3-105">Members</span></span>  
  
|<span data-ttu-id="c06a3-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c06a3-106">Member</span></span>|<span data-ttu-id="c06a3-107">説明</span><span class="sxs-lookup"><span data-stu-id="c06a3-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="c06a3-108">メソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="c06a3-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="c06a3-109">メソッドが移動された行の数。</span><span class="sxs-lookup"><span data-stu-id="c06a3-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c06a3-110">要件</span><span class="sxs-lookup"><span data-stu-id="c06a3-110">Requirements</span></span>  
 <span data-ttu-id="c06a3-111">**ヘッダー:** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="c06a3-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06a3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c06a3-112">See also</span></span>

- [<span data-ttu-id="c06a3-113">シンボル ストア診断構造体</span><span class="sxs-lookup"><span data-stu-id="c06a3-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
