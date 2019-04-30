---
title: BucketParameters 構造体
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5998ce684726b2386d8f1e05eb7eaeccf455747c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946769"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="9a9b9-102">BucketParameters 構造体</span><span class="sxs-lookup"><span data-stu-id="9a9b9-102">BucketParameters Structure</span></span>
<span data-ttu-id="9a9b9-103">イベントに関連付けられている現在の例外のイベントと、パラメーターの型名を格納します。</span><span class="sxs-lookup"><span data-stu-id="9a9b9-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a9b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a9b9-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="9a9b9-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9a9b9-105">Members</span></span>  
  
|<span data-ttu-id="9a9b9-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9a9b9-106">Member</span></span>|<span data-ttu-id="9a9b9-107">説明</span><span class="sxs-lookup"><span data-stu-id="9a9b9-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="9a9b9-108">`true`、この構造体の残りの部分が有効な場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="9a9b9-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="9a9b9-109">イベントの種類の名前です。</span><span class="sxs-lookup"><span data-stu-id="9a9b9-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="9a9b9-110">文字列の配列、各イベントに関連付けられている現在の例外のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a9b9-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a9b9-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a9b9-111">Requirements</span></span>  
 <span data-ttu-id="9a9b9-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a9b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a9b9-113">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="9a9b9-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9a9b9-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a9b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9b9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a9b9-115">See also</span></span>

- [<span data-ttu-id="9a9b9-116">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="9a9b9-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
