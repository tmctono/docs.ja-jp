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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c797378f5e13f39c1c786237a3a7b9cf577fccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763651"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="0e749-102">CorSymVarFlag 列挙体</span><span class="sxs-lookup"><span data-stu-id="0e749-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="0e749-103">変数がコンパイラによって生成されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e749-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e749-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e749-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="0e749-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0e749-105">Members</span></span>  
  
|<span data-ttu-id="0e749-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0e749-106">Member</span></span>|<span data-ttu-id="0e749-107">説明</span><span class="sxs-lookup"><span data-stu-id="0e749-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="0e749-108">指定された変数がコンパイラによって生成されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="0e749-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e749-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0e749-109">Requirements</span></span>  
 <span data-ttu-id="0e749-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0e749-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e749-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e749-111">See also</span></span>

- [<span data-ttu-id="0e749-112">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="0e749-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
