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
ms.openlocfilehash: 21e92d8f2fb80c4c41d516ef281bf4fc8a75f4e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176644"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="7456a-102">CorSymVarFlag 列挙体</span><span class="sxs-lookup"><span data-stu-id="7456a-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="7456a-103">変数がコンパイラで生成されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7456a-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7456a-104">構文</span><span class="sxs-lookup"><span data-stu-id="7456a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="7456a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7456a-105">Members</span></span>  
  
|<span data-ttu-id="7456a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7456a-106">Member</span></span>|<span data-ttu-id="7456a-107">説明</span><span class="sxs-lookup"><span data-stu-id="7456a-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="7456a-108">指定された変数がコンパイラによって生成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="7456a-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7456a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="7456a-109">Requirements</span></span>  
 <span data-ttu-id="7456a-110">**ヘッダー:** コーシム.idl,コーシム.h</span><span class="sxs-lookup"><span data-stu-id="7456a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7456a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7456a-111">See also</span></span>

- [<span data-ttu-id="7456a-112">シンボル ストア診断列挙体</span><span class="sxs-lookup"><span data-stu-id="7456a-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
