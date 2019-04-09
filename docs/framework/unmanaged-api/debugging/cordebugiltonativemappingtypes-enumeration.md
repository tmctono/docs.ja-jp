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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f62707fb1e52a96cf3f131e9c11fee82ab03f4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097188"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="71dc4-102">CorDebugIlToNativeMappingTypes 列挙型</span><span class="sxs-lookup"><span data-stu-id="71dc4-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="71dc4-103">COR_DEBUG_IL_TO_NATIVE_MAP 構造体のインスタンスによって表されるネイティブの命令の特定の範囲が特別なコード領域に対応するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="71dc4-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71dc4-104">構文</span><span class="sxs-lookup"><span data-stu-id="71dc4-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="71dc4-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="71dc4-105">Members</span></span>  
  
|<span data-ttu-id="71dc4-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="71dc4-106">Member</span></span>|<span data-ttu-id="71dc4-107">説明</span><span class="sxs-lookup"><span data-stu-id="71dc4-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="71dc4-108">ネイティブ命令の範囲は、特別なコードの任意のリージョンに対応していません。</span><span class="sxs-lookup"><span data-stu-id="71dc4-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="71dc4-109">ネイティブ命令の範囲は、プロローグに対応します。</span><span class="sxs-lookup"><span data-stu-id="71dc4-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="71dc4-110">ネイティブ命令の範囲は、エピローグに対応します。</span><span class="sxs-lookup"><span data-stu-id="71dc4-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71dc4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="71dc4-111">Requirements</span></span>  
 <span data-ttu-id="71dc4-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71dc4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71dc4-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71dc4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71dc4-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71dc4-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="71dc4-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="71dc4-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71dc4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="71dc4-116">See also</span></span>

- [<span data-ttu-id="71dc4-117">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="71dc4-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="71dc4-118">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="71dc4-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
