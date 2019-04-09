---
title: CorDebugGuidToTypeMapping 構造体
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dc7093edaf12e801a1e1adc52b0be823ff92b91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079917"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="7062d-102">CorDebugGuidToTypeMapping 構造体</span><span class="sxs-lookup"><span data-stu-id="7062d-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="7062d-103">マップを[!INCLUDE[wrt](../../../../includes/wrt-md.md)]を対応する ICorDebugType オブジェクトの GUID。</span><span class="sxs-lookup"><span data-stu-id="7062d-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7062d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7062d-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="7062d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7062d-105">Members</span></span>  
  
|<span data-ttu-id="7062d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7062d-106">Member</span></span>|<span data-ttu-id="7062d-107">説明</span><span class="sxs-lookup"><span data-stu-id="7062d-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="7062d-108">キャッシュされた GUID[!INCLUDE[wrt](../../../../includes/wrt-md.md)]型。</span><span class="sxs-lookup"><span data-stu-id="7062d-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="7062d-109">キャッシュされている型に関する情報を提供する ICorDebugType オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7062d-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7062d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="7062d-110">Requirements</span></span>  
 <span data-ttu-id="7062d-111">**プラットフォーム:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7062d-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="7062d-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7062d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7062d-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7062d-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7062d-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="7062d-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7062d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7062d-115">See also</span></span>

- [<span data-ttu-id="7062d-116">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="7062d-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="7062d-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7062d-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
