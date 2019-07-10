---
title: CorValidatorModuleType 列挙型
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04bed418d96658e29328cf2ce6bba445639b437f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750760"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="8c984-102">CorValidatorModuleType 列挙型</span><span class="sxs-lookup"><span data-stu-id="8c984-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="8c984-103">モジュールの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c984-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c984-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c984-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="8c984-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c984-105">Members</span></span>  
  
|<span data-ttu-id="8c984-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c984-106">Member</span></span>|<span data-ttu-id="8c984-107">説明</span><span class="sxs-lookup"><span data-stu-id="8c984-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="8c984-108">モジュールは、型が無効です。</span><span class="sxs-lookup"><span data-stu-id="8c984-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="8c984-109">最小値、`CorValidatorModuleType`列挙型。</span><span class="sxs-lookup"><span data-stu-id="8c984-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="8c984-110">モジュールは、ポータブル実行可能 (PE) ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8c984-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="8c984-111">モジュールは、.obj ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8c984-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="8c984-112">モジュールでは、デバッガーのエディット コンティニュ セッションです。</span><span class="sxs-lookup"><span data-stu-id="8c984-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="8c984-113">モジュールは、いずれかの段階的に構築されています。</span><span class="sxs-lookup"><span data-stu-id="8c984-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="8c984-114">最大値、`CorValidatorModuleType`列挙型。</span><span class="sxs-lookup"><span data-stu-id="8c984-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c984-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c984-115">Requirements</span></span>  
 <span data-ttu-id="8c984-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c984-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c984-117">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8c984-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c984-118">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8c984-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c984-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c984-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c984-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c984-120">See also</span></span>

- [<span data-ttu-id="8c984-121">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="8c984-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
