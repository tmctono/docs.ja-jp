---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyToken メソッド
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cc02c1f69235403e2f5df28168e17a70f183682
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762415"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="e441c-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken メソッド</span><span class="sxs-lookup"><span data-stu-id="e441c-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="e441c-103">アセンブリの公開キー トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e441c-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e441c-104">構文</span><span class="sxs-lookup"><span data-stu-id="e441c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e441c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e441c-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="e441c-106">[in] `pbPublicKeyToken` 配列の最大バイト数。</span><span class="sxs-lookup"><span data-stu-id="e441c-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="e441c-107">[out] `pbPublicKeyToken` 配列への実際の書き込みバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e441c-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="e441c-108">[out] アセンブリの公開キー トークンを含むバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e441c-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e441c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e441c-109">Remarks</span></span>  
 <span data-ttu-id="e441c-110">アセンブリの公開キー トークンは、その公開キーの SHA1 ハッシュの最後の 8 バイトです。</span><span class="sxs-lookup"><span data-stu-id="e441c-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e441c-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e441c-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e441c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="e441c-112">Requirements</span></span>  
 <span data-ttu-id="e441c-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e441c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e441c-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e441c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e441c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e441c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e441c-116">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e441c-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e441c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e441c-117">See also</span></span>

- [<span data-ttu-id="e441c-118">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e441c-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="e441c-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e441c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
