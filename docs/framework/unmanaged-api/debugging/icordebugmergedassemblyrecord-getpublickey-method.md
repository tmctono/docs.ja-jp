---
title: Icordebugmergedassemblyrecord::getpublickey メソッド
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610e46d5cb550a266c5558c49239d1818c1e85de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107277"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="8b488-102">Icordebugmergedassemblyrecord::getpublickey メソッド</span><span class="sxs-lookup"><span data-stu-id="8b488-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="8b488-103">アセンブリの公開キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b488-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b488-104">構文</span><span class="sxs-lookup"><span data-stu-id="8b488-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b488-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b488-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="8b488-106">[in] `pbPublicKey` 配列の最大バイト数。</span><span class="sxs-lookup"><span data-stu-id="8b488-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="8b488-107">[out] `pbPublicKey` 配列への実際の書き込みバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8b488-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="8b488-108">[out] アセンブリの公開キーを含むバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8b488-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b488-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b488-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b488-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b488-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b488-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8b488-111">Requirements</span></span>  
 <span data-ttu-id="8b488-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b488-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b488-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b488-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b488-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b488-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8b488-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8b488-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8b488-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b488-116">See also</span></span>

- [<span data-ttu-id="8b488-117">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b488-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="8b488-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b488-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
