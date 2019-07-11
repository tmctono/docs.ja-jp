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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38c0937804eb82d1c96a605b55a00784ba58fe13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781827"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="6e222-102">CorImportOptions 列挙型</span><span class="sxs-lookup"><span data-stu-id="6e222-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="6e222-103">現在のスコープ外のアセンブリのインポート中の動作を制御するフラグ値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="6e222-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e222-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e222-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6e222-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e222-105">Members</span></span>  
  
|<span data-ttu-id="6e222-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e222-106">Member</span></span>|<span data-ttu-id="6e222-107">説明</span><span class="sxs-lookup"><span data-stu-id="6e222-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="6e222-108">削除されたレコードをスキップするには既定の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="6e222-109">すべてのメタデータが列挙されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="6e222-110">削除されたものも含めて、すべての Typedef が列挙されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="6e222-111">削除されたものも含めて、すべての MethodDefs が列挙されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="6e222-112">削除されたものも含めて、すべての FieldDefs が列挙されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="6e222-113">削除されたものも含めて、すべての PropertyDefs が列挙されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="6e222-114">削除されたものも含めて、すべての EventDefs が列挙されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="6e222-115">削除されたものを含むすべてのカスタム属性が列挙されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="6e222-116">削除されたものも含めて、すべてのエクスポートされた型が列挙されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e222-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e222-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e222-117">Requirements</span></span>  
 <span data-ttu-id="6e222-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e222-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e222-119">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6e222-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6e222-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e222-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e222-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e222-121">See also</span></span>

- [<span data-ttu-id="6e222-122">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="6e222-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
