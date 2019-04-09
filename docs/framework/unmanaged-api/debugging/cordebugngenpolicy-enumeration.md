---
title: CorDebugNGenPolicy 列挙型
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca922d8b582c0608073d4fd0ba986167ae470e34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109669"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="ed91a-102">CorDebugNGenPolicy 列挙型</span><span class="sxs-lookup"><span data-stu-id="ed91a-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="ed91a-103">デバッガーがネイティブ イメージ キャッシュからネイティブ (NGen) イメージを読み込むかどうかを指定する値を提供します。</span><span class="sxs-lookup"><span data-stu-id="ed91a-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed91a-104">構文</span><span class="sxs-lookup"><span data-stu-id="ed91a-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="ed91a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ed91a-105">Members</span></span>  
  
|<span data-ttu-id="ed91a-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="ed91a-106">Member name</span></span>|<span data-ttu-id="ed91a-107">説明</span><span class="sxs-lookup"><span data-stu-id="ed91a-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="ed91a-108">[!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)]アプリ、ローカルのネイティブ イメージ キャッシュからのイメージの使用が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ed91a-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="ed91a-109">デスクトップ アプリケーションでは、この設定には効果はありません。</span><span class="sxs-lookup"><span data-stu-id="ed91a-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed91a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed91a-110">Remarks</span></span>  
 <span data-ttu-id="ed91a-111">`CorDebugNGENPolicy`列挙型を使用して、 [icordebugprocess 5::enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ed91a-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="ed91a-112">ローカルのネイティブ イメージ キャッシュからのイメージの使用を無効にすると、デバッガーに最適化されたネイティブ イメージではなく、デバッグ可能の JIT コンパイルされたイメージが読み込まれることを確認してデバッグ エクスペリエンスを一貫した提供します。</span><span class="sxs-lookup"><span data-stu-id="ed91a-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed91a-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="ed91a-113">Requirements</span></span>  
 <span data-ttu-id="ed91a-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed91a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed91a-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed91a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed91a-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed91a-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ed91a-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ed91a-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed91a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed91a-118">See also</span></span>

- [<span data-ttu-id="ed91a-119">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="ed91a-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
