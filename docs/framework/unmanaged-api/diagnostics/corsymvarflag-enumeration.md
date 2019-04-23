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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198856"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="38ef7-102">CorSymVarFlag 列挙体</span><span class="sxs-lookup"><span data-stu-id="38ef7-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="38ef7-103">変数がコンパイラによって生成されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="38ef7-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ef7-104">構文</span><span class="sxs-lookup"><span data-stu-id="38ef7-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="38ef7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="38ef7-105">Members</span></span>  
  
|<span data-ttu-id="38ef7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="38ef7-106">Member</span></span>|<span data-ttu-id="38ef7-107">説明</span><span class="sxs-lookup"><span data-stu-id="38ef7-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="38ef7-108">指定された変数がコンパイラによって生成されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="38ef7-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38ef7-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="38ef7-109">Requirements</span></span>  
 <span data-ttu-id="38ef7-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="38ef7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ef7-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="38ef7-111">See also</span></span>

- [<span data-ttu-id="38ef7-112">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="38ef7-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
