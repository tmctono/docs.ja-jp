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
ms.openlocfilehash: 8fe6216e11a64ea182d796247d888b862b1e8377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177927"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="10707-102">CorRegFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="10707-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="10707-103">モジュールまたは複合イメージをインストールするときに登録に使用するフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="10707-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10707-104">構文</span><span class="sxs-lookup"><span data-stu-id="10707-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="10707-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="10707-105">Members</span></span>  
  
|<span data-ttu-id="10707-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="10707-106">Member</span></span>|<span data-ttu-id="10707-107">説明</span><span class="sxs-lookup"><span data-stu-id="10707-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="10707-108">ファイルをコピー先にコピーしないように指定します。</span><span class="sxs-lookup"><span data-stu-id="10707-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="10707-109">モジュールまたはコンポジットが構成であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="10707-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="10707-110">モジュールまたは複合がクラス参照を持っていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="10707-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10707-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="10707-111">Requirements</span></span>  
 <span data-ttu-id="10707-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10707-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10707-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="10707-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10707-114">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="10707-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10707-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10707-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10707-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="10707-116">See also</span></span>

- [<span data-ttu-id="10707-117">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="10707-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
