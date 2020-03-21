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
ms.openlocfilehash: 4d9de489bdeb0ab506f56ff08f4afb4cf6d0ab4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178286"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="09ddc-102">BucketParameters 構造体</span><span class="sxs-lookup"><span data-stu-id="09ddc-102">BucketParameters Structure</span></span>
<span data-ttu-id="09ddc-103">イベントの型名と、イベントに関連付けられている現在の例外のパラメーターを格納します。</span><span class="sxs-lookup"><span data-stu-id="09ddc-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09ddc-104">構文</span><span class="sxs-lookup"><span data-stu-id="09ddc-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="09ddc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="09ddc-105">Members</span></span>  
  
|<span data-ttu-id="09ddc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="09ddc-106">Member</span></span>|<span data-ttu-id="09ddc-107">説明</span><span class="sxs-lookup"><span data-stu-id="09ddc-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="09ddc-108">`true`この構造体の残りの部分が有効な場合は、この構造体を参照します。それ以外`false`の場合は、 .</span><span class="sxs-lookup"><span data-stu-id="09ddc-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="09ddc-109">イベントの種類の名前。</span><span class="sxs-lookup"><span data-stu-id="09ddc-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="09ddc-110">イベントに関連付けられている現在の例外のパラメーターを指定する文字列の配列。</span><span class="sxs-lookup"><span data-stu-id="09ddc-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09ddc-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="09ddc-111">Requirements</span></span>  
 <span data-ttu-id="09ddc-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09ddc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09ddc-113">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="09ddc-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="09ddc-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09ddc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ddc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="09ddc-115">See also</span></span>

- [<span data-ttu-id="09ddc-116">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="09ddc-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
