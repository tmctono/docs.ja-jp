---
title: ICorDebugAppDomainEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da1fc949109455cf50767191a99a8a727116f77c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155195"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="d3291-102">ICorDebugAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3291-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="d3291-103">提供、 `Next` 、指定した数を返すメソッド`ICorDebugAppDomainEnum`列挙体の次の場所から始まる値。</span><span class="sxs-lookup"><span data-stu-id="d3291-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="d3291-104">このインターフェイスは、"ICorDebugEnum"のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="d3291-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3291-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d3291-105">Methods</span></span>  
  
|<span data-ttu-id="d3291-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d3291-106">Method</span></span>|<span data-ttu-id="d3291-107">説明</span><span class="sxs-lookup"><span data-stu-id="d3291-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3291-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="d3291-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="d3291-109">現在のカーソル位置から、コレクションから指定されたアプリケーション ドメイン数を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3291-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3291-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3291-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3291-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d3291-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3291-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d3291-112">Requirements</span></span>  
 <span data-ttu-id="d3291-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3291-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3291-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3291-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3291-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3291-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d3291-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d3291-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3291-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3291-117">See also</span></span>

- [<span data-ttu-id="d3291-118">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3291-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="d3291-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3291-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
