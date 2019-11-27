---
title: CorSymVarFlag 列挙体
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: 86cac53508665c3c97caaa415d8d3c38660928bb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448551"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="f73d0-102">CorSymVarFlag 列挙体</span><span class="sxs-lookup"><span data-stu-id="f73d0-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="f73d0-103">変数がコンパイラによって生成されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f73d0-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f73d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="f73d0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="f73d0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f73d0-105">Members</span></span>  
  
|<span data-ttu-id="f73d0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f73d0-106">Member</span></span>|<span data-ttu-id="f73d0-107">説明</span><span class="sxs-lookup"><span data-stu-id="f73d0-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="f73d0-108">指定された変数がコンパイラによって生成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f73d0-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f73d0-109">要件</span><span class="sxs-lookup"><span data-stu-id="f73d0-109">Requirements</span></span>  
 <span data-ttu-id="f73d0-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="f73d0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f73d0-111">参照</span><span class="sxs-lookup"><span data-stu-id="f73d0-111">See also</span></span>

- [<span data-ttu-id="f73d0-112">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="f73d0-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
