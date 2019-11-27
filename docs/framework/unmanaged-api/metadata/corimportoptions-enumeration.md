---
title: CorImportOptions 列挙型
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: 44d1776e2902988353ef4fd58aca20e56203b9da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442850"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="de4bb-102">CorImportOptions 列挙型</span><span class="sxs-lookup"><span data-stu-id="de4bb-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="de4bb-103">現在のスコープ外のアセンブリのインポート中の動作を制御するフラグ値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="de4bb-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de4bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="de4bb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="de4bb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="de4bb-105">Members</span></span>  
  
|<span data-ttu-id="de4bb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="de4bb-106">Member</span></span>|<span data-ttu-id="de4bb-107">説明</span><span class="sxs-lookup"><span data-stu-id="de4bb-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="de4bb-108">削除されたレコードをスキップする既定の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="de4bb-109">すべてのメタデータを列挙する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="de4bb-110">削除された Typedef も含め、すべての Typedef を列挙する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="de4bb-111">削除されたものを含むすべての MethodDefs を列挙する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="de4bb-112">削除されたものも含め、すべての FieldDefs を列挙する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="de4bb-113">削除されたものも含め、すべての PropertyDefs を列挙する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="de4bb-114">削除されたものも含め、すべての EventDefs を列挙する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="de4bb-115">削除された属性も含め、すべてのカスタム属性を列挙する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="de4bb-116">削除された型も含めて、エクスポートされたすべての型を列挙する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4bb-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de4bb-117">要件</span><span class="sxs-lookup"><span data-stu-id="de4bb-117">Requirements</span></span>  
 <span data-ttu-id="de4bb-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4bb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de4bb-119">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="de4bb-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="de4bb-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de4bb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4bb-121">参照</span><span class="sxs-lookup"><span data-stu-id="de4bb-121">See also</span></span>

- [<span data-ttu-id="de4bb-122">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="de4bb-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
