---
title: ICorDebugDataTarget2::GetImageLocation メソッド
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7acf08262c73df00a96cfb5c244cdfc352e51ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080482"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="5b18e-102">ICorDebugDataTarget2::GetImageLocation メソッド</span><span class="sxs-lookup"><span data-stu-id="5b18e-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="5b18e-103">モジュールのベース アドレスからモジュールのパスを返します。</span><span class="sxs-lookup"><span data-stu-id="5b18e-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b18e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b18e-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b18e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b18e-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="5b18e-106">[in]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)モジュールのベース アドレスを表す値です。</span><span class="sxs-lookup"><span data-stu-id="5b18e-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5b18e-107">[入力] モジュールのパスを受け取るバッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="5b18e-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5b18e-108">[出力] `szName` バッファーに書き込まれる文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5b18e-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="5b18e-109">[出力] モジュールのパス。</span><span class="sxs-lookup"><span data-stu-id="5b18e-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b18e-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b18e-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b18e-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b18e-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b18e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b18e-112">Requirements</span></span>  
 <span data-ttu-id="5b18e-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b18e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b18e-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b18e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b18e-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b18e-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5b18e-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="5b18e-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b18e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b18e-117">See also</span></span>

- [<span data-ttu-id="5b18e-118">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b18e-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="5b18e-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b18e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
