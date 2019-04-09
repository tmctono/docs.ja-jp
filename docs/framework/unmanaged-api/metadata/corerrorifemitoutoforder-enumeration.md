---
title: CorErrorIfEmitOutOfOrder 列挙型
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628ca1b555d80319312450d784981cfed1bda947
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160447"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="ec8fb-102">CorErrorIfEmitOutOfOrder 列挙型</span><span class="sxs-lookup"><span data-stu-id="ec8fb-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="ec8fb-103">メタデータの生成順序が不適切である場合にエラー メッセージが生成される条件を示すフラグ値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec8fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="ec8fb-104">Syntax</span></span>  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="ec8fb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ec8fb-105">Members</span></span>  
  
|<span data-ttu-id="ec8fb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ec8fb-106">Member</span></span>|<span data-ttu-id="ec8fb-107">説明</span><span class="sxs-lookup"><span data-stu-id="ec8fb-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="ec8fb-108">エラー メッセージを生成しない既定の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="ec8fb-109">コンパイラがエラー メッセージを生成しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="ec8fb-110">フィールド、プロパティ、イベント、メソッド、ときに、コンパイラはエラー メッセージを生成する必要がありますか、パラメーターの生成が誤順序のことを示します。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="ec8fb-111">メソッドの生成が順不同の場合に、コンパイラがエラー メッセージを生成することを示します。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="ec8fb-112">フィールドの生成が順不同の場合に、コンパイラがエラー メッセージを生成することを示します。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="ec8fb-113">パラメーターの生成が順不同の場合に、コンパイラがエラー メッセージを生成することを示します。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="ec8fb-114">プロパティの生成が順不同の場合に、コンパイラがエラー メッセージを生成することを示します。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="ec8fb-115">コンパイラが順不同のイベントの生成がエラー メッセージを生成することを示します。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec8fb-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="ec8fb-116">Requirements</span></span>  
 <span data-ttu-id="ec8fb-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec8fb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec8fb-118">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ec8fb-118">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="ec8fb-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ec8fb-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ec8fb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec8fb-120">See also</span></span>

- [<span data-ttu-id="ec8fb-121">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="ec8fb-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
