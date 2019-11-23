---
title: AssemblyRefFlags 列挙型
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
ms.openlocfilehash: 23d293a87112c62cb2127b435faeca258a7de226
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444228"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="f1917-102">AssemblyRefFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="f1917-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="f1917-103">Contains values that describe features of an assembly reference.</span><span class="sxs-lookup"><span data-stu-id="f1917-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1917-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1917-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f1917-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f1917-105">Members</span></span>  
  
|<span data-ttu-id="f1917-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f1917-106">Member</span></span>|<span data-ttu-id="f1917-107">説明</span><span class="sxs-lookup"><span data-stu-id="f1917-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="f1917-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span><span class="sxs-lookup"><span data-stu-id="f1917-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1917-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="f1917-109">Requirements</span></span>  
 <span data-ttu-id="f1917-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1917-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1917-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1917-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1917-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1917-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1917-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1917-113">See also</span></span>

- [<span data-ttu-id="f1917-114">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="f1917-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="f1917-115">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1917-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="f1917-116">DefineAssemblyRef メソッド</span><span class="sxs-lookup"><span data-stu-id="f1917-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
