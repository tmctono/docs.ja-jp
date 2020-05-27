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
ms.openlocfilehash: 1307f555c9d8b6d28febcf25db89ae856c143d71
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009406"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="ed7cf-102">AssemblyRefFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="ed7cf-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="ed7cf-103">アセンブリ参照の機能を記述する値を格納します。</span><span class="sxs-lookup"><span data-stu-id="ed7cf-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="ed7cf-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ed7cf-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ed7cf-105">Members</span></span>  
  
|<span data-ttu-id="ed7cf-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ed7cf-106">Member</span></span>|<span data-ttu-id="ed7cf-107">説明</span><span class="sxs-lookup"><span data-stu-id="ed7cf-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="ed7cf-108">アセンブリ参照に、アセンブリの発行者に関する完全なハッシュされていない情報が含まれることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed7cf-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed7cf-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ed7cf-109">Requirements</span></span>  
 <span data-ttu-id="ed7cf-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed7cf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed7cf-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="ed7cf-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed7cf-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed7cf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7cf-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed7cf-113">See also</span></span>

- [<span data-ttu-id="ed7cf-114">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="ed7cf-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="ed7cf-115">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed7cf-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="ed7cf-116">DefineAssemblyRef メソッド</span><span class="sxs-lookup"><span data-stu-id="ed7cf-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
