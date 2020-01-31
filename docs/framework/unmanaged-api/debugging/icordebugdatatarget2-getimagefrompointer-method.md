---
title: ICorDebugDataTarget2::GetImageFromPointer メソッド
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 55c87731399cf1e7a6747720b8bb33de7e01906c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788844"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="75742-102">ICorDebugDataTarget2::GetImageFromPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="75742-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="75742-103">モジュールのアドレスから、そのモジュールのベース アドレスとサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="75742-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75742-104">構文</span><span class="sxs-lookup"><span data-stu-id="75742-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75742-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75742-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="75742-106">モジュール内のアドレスを表す[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)値。</span><span class="sxs-lookup"><span data-stu-id="75742-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="75742-107">入出力モジュールのベースアドレスを表す[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)値。</span><span class="sxs-lookup"><span data-stu-id="75742-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="75742-108">モジュールのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="75742-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75742-109">コメント</span><span class="sxs-lookup"><span data-stu-id="75742-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75742-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="75742-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75742-111">要件</span><span class="sxs-lookup"><span data-stu-id="75742-111">Requirements</span></span>  
 <span data-ttu-id="75742-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75742-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75742-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75742-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75742-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75742-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75742-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75742-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75742-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="75742-116">See also</span></span>

- [<span data-ttu-id="75742-117">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75742-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="75742-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75742-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
