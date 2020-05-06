---
title: CorDebugIlToNativeMappingTypes 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
ms.openlocfilehash: 808fc70a308eff1b05aa49ea2bb89fe53377c973
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795847"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="114d7-102">CorDebugIlToNativeMappingTypes 列挙型</span><span class="sxs-lookup"><span data-stu-id="114d7-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="114d7-103">COR_DEBUG_IL_TO_NATIVE_MAP 構造体のインスタンスによって表されるネイティブ命令の特定の範囲が、特別なコード領域に対応するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="114d7-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="114d7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="114d7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="114d7-105">Members</span></span>  
  
|<span data-ttu-id="114d7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="114d7-106">Member</span></span>|<span data-ttu-id="114d7-107">説明</span><span class="sxs-lookup"><span data-stu-id="114d7-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="114d7-108">ネイティブ命令の範囲は、特別なコード領域には対応していません。</span><span class="sxs-lookup"><span data-stu-id="114d7-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="114d7-109">ネイティブ命令の範囲は、プロローグに対応しています。</span><span class="sxs-lookup"><span data-stu-id="114d7-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="114d7-110">ネイティブ命令の範囲は、エピローグに相当します。</span><span class="sxs-lookup"><span data-stu-id="114d7-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="114d7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="114d7-111">Requirements</span></span>  
 <span data-ttu-id="114d7-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="114d7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="114d7-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="114d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="114d7-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="114d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="114d7-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="114d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114d7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="114d7-116">See also</span></span>

- [<span data-ttu-id="114d7-117">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="114d7-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="114d7-118">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="114d7-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
