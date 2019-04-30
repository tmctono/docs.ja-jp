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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc98b2421d23ffd6dfb716a8cc782b46a9d59ce0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043318"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="787c0-102">AssemblyRefFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="787c0-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="787c0-103">アセンブリ参照の機能を記述する値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="787c0-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="787c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="787c0-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="787c0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="787c0-105">Members</span></span>  
  
|<span data-ttu-id="787c0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="787c0-106">Member</span></span>|<span data-ttu-id="787c0-107">説明</span><span class="sxs-lookup"><span data-stu-id="787c0-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="787c0-108">アセンブリ参照にはアセンブリの発行者に関する完全なハッシュされていない情報が含まれているを指定します。</span><span class="sxs-lookup"><span data-stu-id="787c0-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="787c0-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="787c0-109">Requirements</span></span>  
 <span data-ttu-id="787c0-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="787c0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="787c0-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="787c0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="787c0-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="787c0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787c0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="787c0-113">See also</span></span>

- [<span data-ttu-id="787c0-114">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="787c0-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="787c0-115">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="787c0-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="787c0-116">DefineAssemblyRef メソッド</span><span class="sxs-lookup"><span data-stu-id="787c0-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
