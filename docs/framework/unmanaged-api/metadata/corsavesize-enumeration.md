---
title: CorSaveSize 列挙型
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc36468a2016822e884ec3a36a23c75477a00a2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045384"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="7cea4-102">CorSaveSize 列挙型</span><span class="sxs-lookup"><span data-stu-id="7cea4-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="7cea4-103">保存操作のサイズの照会で要求される精度のレベルを示す値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7cea4-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cea4-104">構文</span><span class="sxs-lookup"><span data-stu-id="7cea4-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="7cea4-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7cea4-105">Members</span></span>  
  
|<span data-ttu-id="7cea4-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7cea4-106">Member</span></span>|<span data-ttu-id="7cea4-107">説明</span><span class="sxs-lookup"><span data-stu-id="7cea4-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="7cea4-108">戻り値が正確であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7cea4-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="7cea4-109">戻り値を推定することを指定します。</span><span class="sxs-lookup"><span data-stu-id="7cea4-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="7cea4-110">破棄できる型を削除することを指定します。</span><span class="sxs-lookup"><span data-stu-id="7cea4-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7cea4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7cea4-111">Requirements</span></span>  
 <span data-ttu-id="7cea4-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cea4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cea4-113">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7cea4-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7cea4-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="7cea4-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cea4-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cea4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cea4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cea4-116">See also</span></span>

- [<span data-ttu-id="7cea4-117">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="7cea4-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
