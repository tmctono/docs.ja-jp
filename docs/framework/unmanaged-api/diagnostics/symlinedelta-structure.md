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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fabc8f77b12865d0d971b5934d7de27b52f3e813
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914642"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="034e6-102">SYMLINEDELTA 構造体</span><span class="sxs-lookup"><span data-stu-id="034e6-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="034e6-103">編集の結果として移動されたメソッドに関する情報をシンボル ハンドラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="034e6-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="034e6-104">構文</span><span class="sxs-lookup"><span data-stu-id="034e6-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="034e6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="034e6-105">Members</span></span>  
  
|<span data-ttu-id="034e6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="034e6-106">Member</span></span>|<span data-ttu-id="034e6-107">説明</span><span class="sxs-lookup"><span data-stu-id="034e6-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="034e6-108">メソッドのメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="034e6-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="034e6-109">メソッドが移動された行の数。</span><span class="sxs-lookup"><span data-stu-id="034e6-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="034e6-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="034e6-110">Requirements</span></span>  
 <span data-ttu-id="034e6-111">**ヘッダー:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="034e6-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034e6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="034e6-112">See also</span></span>

- [<span data-ttu-id="034e6-113">シンボル ストア診断構造体</span><span class="sxs-lookup"><span data-stu-id="034e6-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
