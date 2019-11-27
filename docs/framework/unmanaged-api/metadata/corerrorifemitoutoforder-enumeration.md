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
ms.openlocfilehash: 57460ba30a8ce974b5ca89f76796c4dcf49ffecf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443588"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="c6964-102">CorErrorIfEmitOutOfOrder 列挙型</span><span class="sxs-lookup"><span data-stu-id="c6964-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="c6964-103">メタデータの生成順序が不適切である場合にエラー メッセージが生成される条件を示すフラグ値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c6964-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6964-104">構文</span><span class="sxs-lookup"><span data-stu-id="c6964-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="c6964-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c6964-105">Members</span></span>  
  
|<span data-ttu-id="c6964-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c6964-106">Member</span></span>|<span data-ttu-id="c6964-107">説明</span><span class="sxs-lookup"><span data-stu-id="c6964-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="c6964-108">エラーメッセージを生成しない既定の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="c6964-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="c6964-109">コンパイラがエラーメッセージを生成しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c6964-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="c6964-110">フィールド、プロパティ、イベント、メソッド、またはパラメーターが順序どおりに生成されない場合に、コンパイラがエラーメッセージを生成することを示します。</span><span class="sxs-lookup"><span data-stu-id="c6964-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="c6964-111">メソッドが順序どおりに出力されない場合に、コンパイラがエラーメッセージを生成する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c6964-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="c6964-112">フィールドが順序どおりに出力されない場合に、コンパイラがエラーメッセージを生成する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c6964-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="c6964-113">パラメーターが順序どおりに出力されない場合に、コンパイラがエラーメッセージを生成する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c6964-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="c6964-114">プロパティが順序どおりに出力されない場合に、コンパイラがエラーメッセージを生成する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c6964-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="c6964-115">イベントが順序どおりに生成されない場合に、コンパイラがエラーメッセージを生成する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c6964-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6964-116">要件</span><span class="sxs-lookup"><span data-stu-id="c6964-116">Requirements</span></span>  
 <span data-ttu-id="c6964-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6964-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6964-118">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c6964-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c6964-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6964-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6964-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6964-120">See also</span></span>

- [<span data-ttu-id="c6964-121">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="c6964-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
