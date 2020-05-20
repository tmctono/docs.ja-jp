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
ms.openlocfilehash: d41e048b67d4bc7159f6dd5266457651f1658290
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420592"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="96c90-102">CorSymVarFlag 列挙体</span><span class="sxs-lookup"><span data-stu-id="96c90-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="96c90-103">変数がコンパイラによって生成されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="96c90-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c90-104">構文</span><span class="sxs-lookup"><span data-stu-id="96c90-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="96c90-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="96c90-105">Members</span></span>  
  
|<span data-ttu-id="96c90-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="96c90-106">Member</span></span>|<span data-ttu-id="96c90-107">説明</span><span class="sxs-lookup"><span data-stu-id="96c90-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="96c90-108">指定された変数がコンパイラによって生成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="96c90-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96c90-109">要件</span><span class="sxs-lookup"><span data-stu-id="96c90-109">Requirements</span></span>  
 <span data-ttu-id="96c90-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="96c90-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c90-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="96c90-111">See also</span></span>

- [<span data-ttu-id="96c90-112">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="96c90-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
