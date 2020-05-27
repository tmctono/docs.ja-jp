---
title: CorRegFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
ms.openlocfilehash: d8d7a43848929e49a8cb48fb957f37213ac78f2e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007352"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="6ddd2-102">CorRegFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="6ddd2-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="6ddd2-103">モジュールまたは複合イメージをインストールするときに登録に使用されるフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ddd2-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ddd2-104">構文</span><span class="sxs-lookup"><span data-stu-id="6ddd2-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6ddd2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6ddd2-105">Members</span></span>  
  
|<span data-ttu-id="6ddd2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6ddd2-106">Member</span></span>|<span data-ttu-id="6ddd2-107">説明</span><span class="sxs-lookup"><span data-stu-id="6ddd2-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="6ddd2-108">転送先にファイルをコピーしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ddd2-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="6ddd2-109">モジュールまたは複合が構成であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ddd2-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="6ddd2-110">モジュールまたは複合にクラス参照があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ddd2-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ddd2-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ddd2-111">Requirements</span></span>  
 <span data-ttu-id="6ddd2-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ddd2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ddd2-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6ddd2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ddd2-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6ddd2-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ddd2-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ddd2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ddd2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ddd2-116">See also</span></span>

- [<span data-ttu-id="6ddd2-117">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="6ddd2-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
