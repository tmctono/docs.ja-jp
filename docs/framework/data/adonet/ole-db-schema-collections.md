---
title: OLE DB スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783450"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="3e6ce-102">OLE DB スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="3e6ce-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="3e6ce-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 OLE DB プロバイダーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e6ce-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="3e6ce-104">Microsoft SQL Server OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="3e6ce-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="3e6ce-105">Microsoft SQL Server OLE DB ドライバーは、共通のスキーマコレクションに加えて次のスキーマコレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3e6ce-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="3e6ce-106">テーブル</span><span class="sxs-lookup"><span data-stu-id="3e6ce-106">Tables</span></span>  
  
- <span data-ttu-id="3e6ce-107">[列]</span><span class="sxs-lookup"><span data-stu-id="3e6ce-107">Columns</span></span>  
  
- <span data-ttu-id="3e6ce-108">手順</span><span class="sxs-lookup"><span data-stu-id="3e6ce-108">Procedures</span></span>  
  
- <span data-ttu-id="3e6ce-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3e6ce-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="3e6ce-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="3e6ce-110">Catalog</span></span>  
  
- <span data-ttu-id="3e6ce-111">インデックス</span><span class="sxs-lookup"><span data-stu-id="3e6ce-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="3e6ce-112">テーブル</span><span class="sxs-lookup"><span data-stu-id="3e6ce-112">Tables</span></span>  
  
|<span data-ttu-id="3e6ce-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-113">ColumnName</span></span>|<span data-ttu-id="3e6ce-114">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-115">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-116">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-116">String</span></span>|  
|<span data-ttu-id="3e6ce-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-118">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-118">String</span></span>|  
|<span data-ttu-id="3e6ce-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-119">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-120">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-120">String</span></span>|  
|<span data-ttu-id="3e6ce-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-121">TABLE_TYPE</span></span>|<span data-ttu-id="3e6ce-122">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-122">String</span></span>|  
|<span data-ttu-id="3e6ce-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-123">TABLE_GUID</span></span>|<span data-ttu-id="3e6ce-124">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-124">Guid</span></span>|  
|<span data-ttu-id="3e6ce-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-125">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-126">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-126">String</span></span>|  
|<span data-ttu-id="3e6ce-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-127">TABLE_PROPID</span></span>|<span data-ttu-id="3e6ce-128">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-128">Int64</span></span>|  
|<span data-ttu-id="3e6ce-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-129">DATE_CREATED</span></span>|<span data-ttu-id="3e6ce-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-130">DateTime</span></span>|  
|<span data-ttu-id="3e6ce-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-131">DATE_MODIFIED</span></span>|<span data-ttu-id="3e6ce-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="3e6ce-133">[列]</span><span class="sxs-lookup"><span data-stu-id="3e6ce-133">Columns</span></span>  
  
|<span data-ttu-id="3e6ce-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-134">ColumnName</span></span>|<span data-ttu-id="3e6ce-135">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-136">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-137">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-137">String</span></span>|  
|<span data-ttu-id="3e6ce-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-139">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-139">String</span></span>|  
|<span data-ttu-id="3e6ce-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-140">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-141">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-141">String</span></span>|  
|<span data-ttu-id="3e6ce-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-142">COLUMN_NAME</span></span>|<span data-ttu-id="3e6ce-143">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-143">String</span></span>|  
|<span data-ttu-id="3e6ce-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-144">COLUMN_GUID</span></span>|<span data-ttu-id="3e6ce-145">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-145">Guid</span></span>|  
|<span data-ttu-id="3e6ce-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-146">COLUMN_PROPID</span></span>|<span data-ttu-id="3e6ce-147">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-147">Int64</span></span>|  
|<span data-ttu-id="3e6ce-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="3e6ce-149">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-149">Int64</span></span>|  
|<span data-ttu-id="3e6ce-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="3e6ce-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="3e6ce-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-151">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3e6ce-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="3e6ce-153">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-153">String</span></span>|  
|<span data-ttu-id="3e6ce-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="3e6ce-155">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-155">Int64</span></span>|  
|<span data-ttu-id="3e6ce-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-156">IS_NULLABLE</span></span>|<span data-ttu-id="3e6ce-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-157">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-158">DATA_TYPE</span></span>|<span data-ttu-id="3e6ce-159">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-159">Int32</span></span>|  
|<span data-ttu-id="3e6ce-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-160">TYPE_GUID</span></span>|<span data-ttu-id="3e6ce-161">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-161">Guid</span></span>|  
|<span data-ttu-id="3e6ce-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="3e6ce-163">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-163">Int64</span></span>|  
|<span data-ttu-id="3e6ce-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="3e6ce-165">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-165">Int64</span></span>|  
|<span data-ttu-id="3e6ce-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="3e6ce-167">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-167">Int32</span></span>|  
|<span data-ttu-id="3e6ce-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="3e6ce-169">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-169">Int16</span></span>|  
|<span data-ttu-id="3e6ce-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="3e6ce-171">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-171">Int64</span></span>|  
|<span data-ttu-id="3e6ce-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="3e6ce-173">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-173">String</span></span>|  
|<span data-ttu-id="3e6ce-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="3e6ce-175">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-175">String</span></span>|  
|<span data-ttu-id="3e6ce-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="3e6ce-177">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-177">String</span></span>|  
|<span data-ttu-id="3e6ce-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="3e6ce-179">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-179">String</span></span>|  
|<span data-ttu-id="3e6ce-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="3e6ce-181">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-181">String</span></span>|  
|<span data-ttu-id="3e6ce-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-182">COLLATION_NAME</span></span>|<span data-ttu-id="3e6ce-183">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-183">String</span></span>|  
|<span data-ttu-id="3e6ce-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="3e6ce-185">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-185">String</span></span>|  
|<span data-ttu-id="3e6ce-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="3e6ce-187">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-187">String</span></span>|  
|<span data-ttu-id="3e6ce-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-188">DOMAIN_NAME</span></span>|<span data-ttu-id="3e6ce-189">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-189">String</span></span>|  
|<span data-ttu-id="3e6ce-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-190">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-191">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-191">String</span></span>|  
|<span data-ttu-id="3e6ce-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-192">COLUMN_LCID</span></span>|<span data-ttu-id="3e6ce-193">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-193">Int32</span></span>|  
|<span data-ttu-id="3e6ce-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="3e6ce-195">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-195">Int32</span></span>|  
|<span data-ttu-id="3e6ce-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-196">COLUMN_SORTID</span></span>|<span data-ttu-id="3e6ce-197">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-197">Int32</span></span>|  
|<span data-ttu-id="3e6ce-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="3e6ce-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="3e6ce-199">Byte[]</span></span>|  
|<span data-ttu-id="3e6ce-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-200">IS_COMPUTED</span></span>|<span data-ttu-id="3e6ce-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="3e6ce-202">手順</span><span class="sxs-lookup"><span data-stu-id="3e6ce-202">Procedures</span></span>  
  
|<span data-ttu-id="3e6ce-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-203">ColumnName</span></span>|<span data-ttu-id="3e6ce-204">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="3e6ce-206">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-206">String</span></span>|  
|<span data-ttu-id="3e6ce-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-208">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-208">String</span></span>|  
|<span data-ttu-id="3e6ce-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="3e6ce-210">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-210">String</span></span>|  
|<span data-ttu-id="3e6ce-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3e6ce-212">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-212">Int16</span></span>|  
|<span data-ttu-id="3e6ce-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="3e6ce-214">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-214">String</span></span>|  
|<span data-ttu-id="3e6ce-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-215">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-216">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-216">String</span></span>|  
|<span data-ttu-id="3e6ce-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-217">DATE_CREATED</span></span>|<span data-ttu-id="3e6ce-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-218">DateTime</span></span>|  
|<span data-ttu-id="3e6ce-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-219">DATE_MODIFIED</span></span>|<span data-ttu-id="3e6ce-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="3e6ce-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3e6ce-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="3e6ce-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-222">ColumnName</span></span>|<span data-ttu-id="3e6ce-223">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="3e6ce-225">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-225">String</span></span>|  
|<span data-ttu-id="3e6ce-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-227">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-227">String</span></span>|  
|<span data-ttu-id="3e6ce-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="3e6ce-229">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-229">String</span></span>|  
|<span data-ttu-id="3e6ce-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-230">PARAMETER_NAME</span></span>|<span data-ttu-id="3e6ce-231">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-231">String</span></span>|  
|<span data-ttu-id="3e6ce-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="3e6ce-233">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-233">Int32</span></span>|  
|<span data-ttu-id="3e6ce-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="3e6ce-235">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-235">Int32</span></span>|  
|<span data-ttu-id="3e6ce-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="3e6ce-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="3e6ce-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-237">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3e6ce-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="3e6ce-239">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-239">String</span></span>|  
|<span data-ttu-id="3e6ce-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-240">IS_NULLABLE</span></span>|<span data-ttu-id="3e6ce-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-241">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-242">DATA_TYPE</span></span>|<span data-ttu-id="3e6ce-243">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-243">Int32</span></span>|  
|<span data-ttu-id="3e6ce-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="3e6ce-245">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-245">Int64</span></span>|  
|<span data-ttu-id="3e6ce-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="3e6ce-247">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-247">Int64</span></span>|  
|<span data-ttu-id="3e6ce-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="3e6ce-249">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-249">Int32</span></span>|  
|<span data-ttu-id="3e6ce-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="3e6ce-251">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-251">Int16</span></span>|  
|<span data-ttu-id="3e6ce-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-252">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-253">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-253">String</span></span>|  
|<span data-ttu-id="3e6ce-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-254">TYPE_NAME</span></span>|<span data-ttu-id="3e6ce-255">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-255">String</span></span>|  
|<span data-ttu-id="3e6ce-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="3e6ce-257">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="3e6ce-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="3e6ce-258">Catalog</span></span>  
  
|<span data-ttu-id="3e6ce-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-259">ColumnName</span></span>|<span data-ttu-id="3e6ce-260">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-261">CATALOG_NAME</span></span>|<span data-ttu-id="3e6ce-262">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-262">String</span></span>|  
|<span data-ttu-id="3e6ce-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-263">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-264">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="3e6ce-265">インデックス</span><span class="sxs-lookup"><span data-stu-id="3e6ce-265">Indexes</span></span>  
  
|<span data-ttu-id="3e6ce-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-266">ColumnName</span></span>|<span data-ttu-id="3e6ce-267">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-268">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-269">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-269">String</span></span>|  
|<span data-ttu-id="3e6ce-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-271">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-271">String</span></span>|  
|<span data-ttu-id="3e6ce-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-272">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-273">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-273">String</span></span>|  
|<span data-ttu-id="3e6ce-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-274">INDEX_CATALOG</span></span>|<span data-ttu-id="3e6ce-275">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-275">String</span></span>|  
|<span data-ttu-id="3e6ce-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="3e6ce-277">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-277">String</span></span>|  
|<span data-ttu-id="3e6ce-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-278">INDEX_NAME</span></span>|<span data-ttu-id="3e6ce-279">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-279">String</span></span>|  
|<span data-ttu-id="3e6ce-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="3e6ce-280">PRIMARY_KEY</span></span>|<span data-ttu-id="3e6ce-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-281">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-282">UNIQUE</span></span>|<span data-ttu-id="3e6ce-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-283">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-284">CLUSTERED</span></span>|<span data-ttu-id="3e6ce-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-285">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-286">TYPE</span></span>|<span data-ttu-id="3e6ce-287">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-287">Int32</span></span>|  
|<span data-ttu-id="3e6ce-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="3e6ce-288">FILL_FACTOR</span></span>|<span data-ttu-id="3e6ce-289">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-289">Int32</span></span>|  
|<span data-ttu-id="3e6ce-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-290">INITIAL_SIZE</span></span>|<span data-ttu-id="3e6ce-291">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-291">Int32</span></span>|  
|<span data-ttu-id="3e6ce-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-292">NULLS</span></span>|<span data-ttu-id="3e6ce-293">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-293">Int32</span></span>|  
|<span data-ttu-id="3e6ce-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="3e6ce-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-295">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-296">AUTO_UPDATE</span></span>|<span data-ttu-id="3e6ce-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-297">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-298">NULL_COLLATION</span></span>|<span data-ttu-id="3e6ce-299">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-299">Int32</span></span>|  
|<span data-ttu-id="3e6ce-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="3e6ce-301">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-301">Int64</span></span>|  
|<span data-ttu-id="3e6ce-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-302">COLUMN_NAME</span></span>|<span data-ttu-id="3e6ce-303">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-303">String</span></span>|  
|<span data-ttu-id="3e6ce-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-304">COLUMN_GUID</span></span>|<span data-ttu-id="3e6ce-305">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-305">Guid</span></span>|  
|<span data-ttu-id="3e6ce-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-306">COLUMN_PROPID</span></span>|<span data-ttu-id="3e6ce-307">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-307">Int64</span></span>|  
|<span data-ttu-id="3e6ce-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-308">COLLATION</span></span>|<span data-ttu-id="3e6ce-309">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-309">Int16</span></span>|  
|<span data-ttu-id="3e6ce-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="3e6ce-310">CARDINALITY</span></span>|<span data-ttu-id="3e6ce-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="3e6ce-311">Decimal</span></span>|  
|<span data-ttu-id="3e6ce-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="3e6ce-312">PAGES</span></span>|<span data-ttu-id="3e6ce-313">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-313">Int32</span></span>|  
|<span data-ttu-id="3e6ce-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-314">FILTER_CONDITION</span></span>|<span data-ttu-id="3e6ce-315">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-315">String</span></span>|  
|<span data-ttu-id="3e6ce-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-316">INTEGRATED</span></span>|<span data-ttu-id="3e6ce-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="3e6ce-318">Microsoft Oracle OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="3e6ce-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="3e6ce-319">Microsoft Oracle OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3e6ce-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="3e6ce-320">テーブル</span><span class="sxs-lookup"><span data-stu-id="3e6ce-320">Tables</span></span>  
  
- <span data-ttu-id="3e6ce-321">[列]</span><span class="sxs-lookup"><span data-stu-id="3e6ce-321">Columns</span></span>  
  
- <span data-ttu-id="3e6ce-322">手順</span><span class="sxs-lookup"><span data-stu-id="3e6ce-322">Procedures</span></span>  
  
- <span data-ttu-id="3e6ce-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3e6ce-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="3e6ce-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="3e6ce-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="3e6ce-325">Views</span><span class="sxs-lookup"><span data-stu-id="3e6ce-325">Views</span></span>  
  
- <span data-ttu-id="3e6ce-326">インデックス</span><span class="sxs-lookup"><span data-stu-id="3e6ce-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="3e6ce-327">テーブル</span><span class="sxs-lookup"><span data-stu-id="3e6ce-327">Tables</span></span>  
  
|<span data-ttu-id="3e6ce-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-328">ColumnName</span></span>|<span data-ttu-id="3e6ce-329">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-330">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-331">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-331">String</span></span>|  
|<span data-ttu-id="3e6ce-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-333">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-333">String</span></span>|  
|<span data-ttu-id="3e6ce-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-334">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-335">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-335">String</span></span>|  
|<span data-ttu-id="3e6ce-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-336">TABLE_TYPE</span></span>|<span data-ttu-id="3e6ce-337">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-337">String</span></span>|  
|<span data-ttu-id="3e6ce-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-338">TABLE_GUID</span></span>|<span data-ttu-id="3e6ce-339">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-339">Guid</span></span>|  
|<span data-ttu-id="3e6ce-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-340">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-341">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-341">String</span></span>|  
|<span data-ttu-id="3e6ce-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-342">TABLE_PROPID</span></span>|<span data-ttu-id="3e6ce-343">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-343">Int64</span></span>|  
|<span data-ttu-id="3e6ce-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-344">DATE_CREATED</span></span>|<span data-ttu-id="3e6ce-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-345">DateTime</span></span>|  
|<span data-ttu-id="3e6ce-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-346">DATE_MODIFIED</span></span>|<span data-ttu-id="3e6ce-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="3e6ce-348">[列]</span><span class="sxs-lookup"><span data-stu-id="3e6ce-348">Columns</span></span>  
  
|<span data-ttu-id="3e6ce-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-349">ColumnName</span></span>|<span data-ttu-id="3e6ce-350">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-351">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-352">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-352">String</span></span>|  
|<span data-ttu-id="3e6ce-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-354">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-354">String</span></span>|  
|<span data-ttu-id="3e6ce-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-355">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-356">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-356">String</span></span>|  
|<span data-ttu-id="3e6ce-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-357">COLUMN_NAME</span></span>|<span data-ttu-id="3e6ce-358">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-358">String</span></span>|  
|<span data-ttu-id="3e6ce-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-359">COLUMN_GUID</span></span>|<span data-ttu-id="3e6ce-360">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-360">Guid</span></span>|  
|<span data-ttu-id="3e6ce-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-361">COLUMN_PROPID</span></span>|<span data-ttu-id="3e6ce-362">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-362">Int64</span></span>|  
|<span data-ttu-id="3e6ce-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="3e6ce-364">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-364">Int64</span></span>|  
|<span data-ttu-id="3e6ce-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="3e6ce-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="3e6ce-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-366">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3e6ce-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="3e6ce-368">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-368">String</span></span>|  
|<span data-ttu-id="3e6ce-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="3e6ce-370">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-370">Int64</span></span>|  
|<span data-ttu-id="3e6ce-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-371">IS_NULLABLE</span></span>|<span data-ttu-id="3e6ce-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-372">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-373">DATA_TYPE</span></span>|<span data-ttu-id="3e6ce-374">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-374">Int32</span></span>|  
|<span data-ttu-id="3e6ce-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-375">TYPE_GUID</span></span>|<span data-ttu-id="3e6ce-376">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-376">Guid</span></span>|  
|<span data-ttu-id="3e6ce-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="3e6ce-378">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-378">Int64</span></span>|  
|<span data-ttu-id="3e6ce-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="3e6ce-380">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-380">Int64</span></span>|  
|<span data-ttu-id="3e6ce-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="3e6ce-382">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-382">Int32</span></span>|  
|<span data-ttu-id="3e6ce-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="3e6ce-384">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-384">Int16</span></span>|  
|<span data-ttu-id="3e6ce-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="3e6ce-386">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-386">Int64</span></span>|  
|<span data-ttu-id="3e6ce-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="3e6ce-388">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-388">String</span></span>|  
|<span data-ttu-id="3e6ce-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="3e6ce-390">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-390">String</span></span>|  
|<span data-ttu-id="3e6ce-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="3e6ce-392">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-392">String</span></span>|  
|<span data-ttu-id="3e6ce-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="3e6ce-394">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-394">String</span></span>|  
|<span data-ttu-id="3e6ce-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="3e6ce-396">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-396">String</span></span>|  
|<span data-ttu-id="3e6ce-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-397">COLLATION_NAME</span></span>|<span data-ttu-id="3e6ce-398">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-398">String</span></span>|  
|<span data-ttu-id="3e6ce-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="3e6ce-400">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-400">String</span></span>|  
|<span data-ttu-id="3e6ce-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="3e6ce-402">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-402">String</span></span>|  
|<span data-ttu-id="3e6ce-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-403">DOMAIN_NAME</span></span>|<span data-ttu-id="3e6ce-404">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-404">String</span></span>|  
|<span data-ttu-id="3e6ce-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-405">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-406">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="3e6ce-407">手順</span><span class="sxs-lookup"><span data-stu-id="3e6ce-407">Procedures</span></span>  
  
|<span data-ttu-id="3e6ce-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-408">ColumnName</span></span>|<span data-ttu-id="3e6ce-409">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="3e6ce-411">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-411">String</span></span>|  
|<span data-ttu-id="3e6ce-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-413">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-413">String</span></span>|  
|<span data-ttu-id="3e6ce-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="3e6ce-415">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-415">String</span></span>|  
|<span data-ttu-id="3e6ce-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3e6ce-417">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-417">Int16</span></span>|  
|<span data-ttu-id="3e6ce-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="3e6ce-419">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-419">String</span></span>|  
|<span data-ttu-id="3e6ce-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-420">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-421">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-421">String</span></span>|  
|<span data-ttu-id="3e6ce-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-422">DATE_CREATED</span></span>|<span data-ttu-id="3e6ce-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-423">DateTime</span></span>|  
|<span data-ttu-id="3e6ce-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-424">DATE_MODIFIED</span></span>|<span data-ttu-id="3e6ce-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="3e6ce-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="3e6ce-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="3e6ce-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-427">ColumnName</span></span>|<span data-ttu-id="3e6ce-428">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="3e6ce-430">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-430">String</span></span>|  
|<span data-ttu-id="3e6ce-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-432">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-432">String</span></span>|  
|<span data-ttu-id="3e6ce-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="3e6ce-434">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-434">String</span></span>|  
|<span data-ttu-id="3e6ce-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-435">COLUMN_NAME</span></span>|<span data-ttu-id="3e6ce-436">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-436">String</span></span>|  
|<span data-ttu-id="3e6ce-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-437">COLUMN_GUID</span></span>|<span data-ttu-id="3e6ce-438">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-438">Guid</span></span>|  
|<span data-ttu-id="3e6ce-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-439">COLUMN_PROPID</span></span>|<span data-ttu-id="3e6ce-440">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-440">Int64</span></span>|  
|<span data-ttu-id="3e6ce-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="3e6ce-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="3e6ce-442">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-442">Int64</span></span>|  
|<span data-ttu-id="3e6ce-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="3e6ce-444">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-444">Int64</span></span>|  
|<span data-ttu-id="3e6ce-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-445">IS_NULLABLE</span></span>|<span data-ttu-id="3e6ce-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-446">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-447">DATA_TYPE</span></span>|<span data-ttu-id="3e6ce-448">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-448">Int32</span></span>|  
|<span data-ttu-id="3e6ce-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-449">TYPE_GUID</span></span>|<span data-ttu-id="3e6ce-450">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-450">Guid</span></span>|  
|<span data-ttu-id="3e6ce-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="3e6ce-452">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-452">Int64</span></span>|  
|<span data-ttu-id="3e6ce-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="3e6ce-454">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-454">Int64</span></span>|  
|<span data-ttu-id="3e6ce-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="3e6ce-456">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-456">Int32</span></span>|  
|<span data-ttu-id="3e6ce-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="3e6ce-458">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-458">Int16</span></span>|  
|<span data-ttu-id="3e6ce-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-459">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-460">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-460">String</span></span>|  
|<span data-ttu-id="3e6ce-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="3e6ce-461">OVERLOAD</span></span>|<span data-ttu-id="3e6ce-462">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="3e6ce-463">Views</span><span class="sxs-lookup"><span data-stu-id="3e6ce-463">Views</span></span>  
  
|<span data-ttu-id="3e6ce-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-464">ColumnName</span></span>|<span data-ttu-id="3e6ce-465">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-466">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-467">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-467">String</span></span>|  
|<span data-ttu-id="3e6ce-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-469">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-469">String</span></span>|  
|<span data-ttu-id="3e6ce-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-470">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-471">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-471">String</span></span>|  
|<span data-ttu-id="3e6ce-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="3e6ce-473">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-473">String</span></span>|  
|<span data-ttu-id="3e6ce-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-474">CHECK_OPTION</span></span>|<span data-ttu-id="3e6ce-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-475">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-476">IS_UPDATABLE</span></span>|<span data-ttu-id="3e6ce-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-477">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-478">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-479">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-479">String</span></span>|  
|<span data-ttu-id="3e6ce-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-480">DATE_CREATED</span></span>|<span data-ttu-id="3e6ce-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-481">DateTime</span></span>|  
|<span data-ttu-id="3e6ce-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-482">DATE_MODIFIED</span></span>|<span data-ttu-id="3e6ce-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="3e6ce-484">インデックス</span><span class="sxs-lookup"><span data-stu-id="3e6ce-484">Indexes</span></span>  
  
|<span data-ttu-id="3e6ce-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-485">ColumnName</span></span>|<span data-ttu-id="3e6ce-486">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-487">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-488">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-488">String</span></span>|  
|<span data-ttu-id="3e6ce-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-490">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-490">String</span></span>|  
|<span data-ttu-id="3e6ce-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-491">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-492">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-492">String</span></span>|  
|<span data-ttu-id="3e6ce-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-493">INDEX_CATALOG</span></span>|<span data-ttu-id="3e6ce-494">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-494">String</span></span>|  
|<span data-ttu-id="3e6ce-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="3e6ce-496">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-496">String</span></span>|  
|<span data-ttu-id="3e6ce-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-497">INDEX_NAME</span></span>|<span data-ttu-id="3e6ce-498">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-498">String</span></span>|  
|<span data-ttu-id="3e6ce-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="3e6ce-499">PRIMARY_KEY</span></span>|<span data-ttu-id="3e6ce-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-500">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-501">UNIQUE</span></span>|<span data-ttu-id="3e6ce-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-502">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-503">CLUSTERED</span></span>|<span data-ttu-id="3e6ce-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-504">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-505">TYPE</span></span>|<span data-ttu-id="3e6ce-506">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-506">Int32</span></span>|  
|<span data-ttu-id="3e6ce-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="3e6ce-507">FILL_FACTOR</span></span>|<span data-ttu-id="3e6ce-508">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-508">Int32</span></span>|  
|<span data-ttu-id="3e6ce-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-509">INITIAL_SIZE</span></span>|<span data-ttu-id="3e6ce-510">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-510">Int32</span></span>|  
|<span data-ttu-id="3e6ce-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-511">NULLS</span></span>|<span data-ttu-id="3e6ce-512">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-512">Int32</span></span>|  
|<span data-ttu-id="3e6ce-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="3e6ce-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-514">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-515">AUTO_UPDATE</span></span>|<span data-ttu-id="3e6ce-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-516">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-517">NULL_COLLATION</span></span>|<span data-ttu-id="3e6ce-518">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-518">Int32</span></span>|  
|<span data-ttu-id="3e6ce-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="3e6ce-520">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-520">Int64</span></span>|  
|<span data-ttu-id="3e6ce-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-521">COLUMN_NAME</span></span>|<span data-ttu-id="3e6ce-522">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-522">String</span></span>|  
|<span data-ttu-id="3e6ce-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-523">COLUMN_GUID</span></span>|<span data-ttu-id="3e6ce-524">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-524">Guid</span></span>|  
|<span data-ttu-id="3e6ce-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-525">COLUMN_PROPID</span></span>|<span data-ttu-id="3e6ce-526">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-526">Int64</span></span>|  
|<span data-ttu-id="3e6ce-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-527">COLLATION</span></span>|<span data-ttu-id="3e6ce-528">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-528">Int16</span></span>|  
|<span data-ttu-id="3e6ce-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="3e6ce-529">CARDINALITY</span></span>|<span data-ttu-id="3e6ce-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="3e6ce-530">Decimal</span></span>|  
|<span data-ttu-id="3e6ce-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="3e6ce-531">PAGES</span></span>|<span data-ttu-id="3e6ce-532">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-532">Int32</span></span>|  
|<span data-ttu-id="3e6ce-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-533">FILTER_CONDITION</span></span>|<span data-ttu-id="3e6ce-534">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-534">String</span></span>|  
|<span data-ttu-id="3e6ce-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-535">INTEGRATED</span></span>|<span data-ttu-id="3e6ce-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="3e6ce-537">Microsoft Jet OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="3e6ce-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="3e6ce-538">Microsoft Jet OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3e6ce-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="3e6ce-539">テーブル</span><span class="sxs-lookup"><span data-stu-id="3e6ce-539">Tables</span></span>  
  
- <span data-ttu-id="3e6ce-540">[列]</span><span class="sxs-lookup"><span data-stu-id="3e6ce-540">Columns</span></span>  
  
- <span data-ttu-id="3e6ce-541">手順</span><span class="sxs-lookup"><span data-stu-id="3e6ce-541">Procedures</span></span>  
  
- <span data-ttu-id="3e6ce-542">Views</span><span class="sxs-lookup"><span data-stu-id="3e6ce-542">Views</span></span>  
  
- <span data-ttu-id="3e6ce-543">インデックス</span><span class="sxs-lookup"><span data-stu-id="3e6ce-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="3e6ce-544">テーブル</span><span class="sxs-lookup"><span data-stu-id="3e6ce-544">Tables</span></span>  
  
|<span data-ttu-id="3e6ce-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-545">ColumnName</span></span>|<span data-ttu-id="3e6ce-546">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-547">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-548">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-548">String</span></span>|  
|<span data-ttu-id="3e6ce-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-550">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-550">String</span></span>|  
|<span data-ttu-id="3e6ce-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-551">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-552">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-552">String</span></span>|  
|<span data-ttu-id="3e6ce-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-553">TABLE_TYPE</span></span>|<span data-ttu-id="3e6ce-554">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-554">String</span></span>|  
|<span data-ttu-id="3e6ce-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-555">TABLE_GUID</span></span>|<span data-ttu-id="3e6ce-556">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-556">Guid</span></span>|  
|<span data-ttu-id="3e6ce-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-557">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-558">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-558">String</span></span>|  
|<span data-ttu-id="3e6ce-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-559">TABLE_PROPID</span></span>|<span data-ttu-id="3e6ce-560">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-560">Int64</span></span>|  
|<span data-ttu-id="3e6ce-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-561">DATE_CREATED</span></span>|<span data-ttu-id="3e6ce-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-562">DateTime</span></span>|  
|<span data-ttu-id="3e6ce-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-563">DATE_MODIFIED</span></span>|<span data-ttu-id="3e6ce-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="3e6ce-565">[列]</span><span class="sxs-lookup"><span data-stu-id="3e6ce-565">Columns</span></span>  
  
|<span data-ttu-id="3e6ce-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-566">ColumnName</span></span>|<span data-ttu-id="3e6ce-567">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-568">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-569">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-569">String</span></span>|  
|<span data-ttu-id="3e6ce-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-571">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-571">String</span></span>|  
|<span data-ttu-id="3e6ce-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-572">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-573">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-573">String</span></span>|  
|<span data-ttu-id="3e6ce-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-574">COLUMN_NAME</span></span>|<span data-ttu-id="3e6ce-575">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-575">String</span></span>|  
|<span data-ttu-id="3e6ce-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-576">COLUMN_GUID</span></span>|<span data-ttu-id="3e6ce-577">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-577">Guid</span></span>|  
|<span data-ttu-id="3e6ce-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-578">COLUMN_PROPID</span></span>|<span data-ttu-id="3e6ce-579">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-579">Int64</span></span>|  
|<span data-ttu-id="3e6ce-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="3e6ce-581">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-581">Int64</span></span>|  
|<span data-ttu-id="3e6ce-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="3e6ce-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="3e6ce-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-583">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3e6ce-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="3e6ce-585">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-585">String</span></span>|  
|<span data-ttu-id="3e6ce-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="3e6ce-587">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-587">Int64</span></span>|  
|<span data-ttu-id="3e6ce-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-588">IS_NULLABLE</span></span>|<span data-ttu-id="3e6ce-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-589">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-590">DATA_TYPE</span></span>|<span data-ttu-id="3e6ce-591">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-591">Int32</span></span>|  
|<span data-ttu-id="3e6ce-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-592">TYPE_GUID</span></span>|<span data-ttu-id="3e6ce-593">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-593">Guid</span></span>|  
|<span data-ttu-id="3e6ce-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="3e6ce-595">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-595">Int64</span></span>|  
|<span data-ttu-id="3e6ce-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3e6ce-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="3e6ce-597">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-597">Int64</span></span>|  
|<span data-ttu-id="3e6ce-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="3e6ce-599">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-599">Int32</span></span>|  
|<span data-ttu-id="3e6ce-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="3e6ce-601">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-601">Int16</span></span>|  
|<span data-ttu-id="3e6ce-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="3e6ce-603">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-603">Int64</span></span>|  
|<span data-ttu-id="3e6ce-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="3e6ce-605">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-605">String</span></span>|  
|<span data-ttu-id="3e6ce-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="3e6ce-607">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-607">String</span></span>|  
|<span data-ttu-id="3e6ce-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="3e6ce-609">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-609">String</span></span>|  
|<span data-ttu-id="3e6ce-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="3e6ce-611">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-611">String</span></span>|  
|<span data-ttu-id="3e6ce-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="3e6ce-613">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-613">String</span></span>|  
|<span data-ttu-id="3e6ce-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-614">COLLATION_NAME</span></span>|<span data-ttu-id="3e6ce-615">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-615">String</span></span>|  
|<span data-ttu-id="3e6ce-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="3e6ce-617">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-617">String</span></span>|  
|<span data-ttu-id="3e6ce-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="3e6ce-619">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-619">String</span></span>|  
|<span data-ttu-id="3e6ce-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-620">DOMAIN_NAME</span></span>|<span data-ttu-id="3e6ce-621">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-621">String</span></span>|  
|<span data-ttu-id="3e6ce-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-622">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-623">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="3e6ce-624">手順</span><span class="sxs-lookup"><span data-stu-id="3e6ce-624">Procedures</span></span>  
  
|<span data-ttu-id="3e6ce-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-625">ColumnName</span></span>|<span data-ttu-id="3e6ce-626">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="3e6ce-628">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-628">String</span></span>|  
|<span data-ttu-id="3e6ce-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-630">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-630">String</span></span>|  
|<span data-ttu-id="3e6ce-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="3e6ce-632">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-632">String</span></span>|  
|<span data-ttu-id="3e6ce-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="3e6ce-634">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-634">Int16</span></span>|  
|<span data-ttu-id="3e6ce-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="3e6ce-636">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-636">String</span></span>|  
|<span data-ttu-id="3e6ce-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-637">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-638">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-638">String</span></span>|  
|<span data-ttu-id="3e6ce-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-639">DATE_CREATED</span></span>|<span data-ttu-id="3e6ce-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-640">DateTime</span></span>|  
|<span data-ttu-id="3e6ce-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-641">DATE_MODIFIED</span></span>|<span data-ttu-id="3e6ce-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="3e6ce-643">Views</span><span class="sxs-lookup"><span data-stu-id="3e6ce-643">Views</span></span>  
  
|<span data-ttu-id="3e6ce-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-644">ColumnName</span></span>|<span data-ttu-id="3e6ce-645">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-646">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-647">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-647">String</span></span>|  
|<span data-ttu-id="3e6ce-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-649">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-649">String</span></span>|  
|<span data-ttu-id="3e6ce-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-650">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-651">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-651">String</span></span>|  
|<span data-ttu-id="3e6ce-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="3e6ce-653">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-653">String</span></span>|  
|<span data-ttu-id="3e6ce-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-654">CHECK_OPTION</span></span>|<span data-ttu-id="3e6ce-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-655">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-656">IS_UPDATABLE</span></span>|<span data-ttu-id="3e6ce-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-657">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-658">DESCRIPTION</span></span>|<span data-ttu-id="3e6ce-659">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-659">String</span></span>|  
|<span data-ttu-id="3e6ce-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-660">DATE_CREATED</span></span>|<span data-ttu-id="3e6ce-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-661">DateTime</span></span>|  
|<span data-ttu-id="3e6ce-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-662">DATE_MODIFIED</span></span>|<span data-ttu-id="3e6ce-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e6ce-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="3e6ce-664">インデックス</span><span class="sxs-lookup"><span data-stu-id="3e6ce-664">Indexes</span></span>  
  
|<span data-ttu-id="3e6ce-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="3e6ce-665">ColumnName</span></span>|<span data-ttu-id="3e6ce-666">DataType</span><span class="sxs-lookup"><span data-stu-id="3e6ce-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="3e6ce-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-667">TABLE_CATALOG</span></span>|<span data-ttu-id="3e6ce-668">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-668">String</span></span>|  
|<span data-ttu-id="3e6ce-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="3e6ce-670">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-670">String</span></span>|  
|<span data-ttu-id="3e6ce-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-671">TABLE_NAME</span></span>|<span data-ttu-id="3e6ce-672">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-672">String</span></span>|  
|<span data-ttu-id="3e6ce-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="3e6ce-673">INDEX_CATALOG</span></span>|<span data-ttu-id="3e6ce-674">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-674">String</span></span>|  
|<span data-ttu-id="3e6ce-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="3e6ce-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="3e6ce-676">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-676">String</span></span>|  
|<span data-ttu-id="3e6ce-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-677">INDEX_NAME</span></span>|<span data-ttu-id="3e6ce-678">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-678">String</span></span>|  
|<span data-ttu-id="3e6ce-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="3e6ce-679">PRIMARY_KEY</span></span>|<span data-ttu-id="3e6ce-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-680">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-681">UNIQUE</span></span>|<span data-ttu-id="3e6ce-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-682">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-683">CLUSTERED</span></span>|<span data-ttu-id="3e6ce-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-684">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-685">TYPE</span></span>|<span data-ttu-id="3e6ce-686">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-686">Int32</span></span>|  
|<span data-ttu-id="3e6ce-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="3e6ce-687">FILL_FACTOR</span></span>|<span data-ttu-id="3e6ce-688">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-688">Int32</span></span>|  
|<span data-ttu-id="3e6ce-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-689">INITIAL_SIZE</span></span>|<span data-ttu-id="3e6ce-690">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-690">Int32</span></span>|  
|<span data-ttu-id="3e6ce-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-691">NULLS</span></span>|<span data-ttu-id="3e6ce-692">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-692">Int32</span></span>|  
|<span data-ttu-id="3e6ce-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="3e6ce-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="3e6ce-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-694">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="3e6ce-695">AUTO_UPDATE</span></span>|<span data-ttu-id="3e6ce-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-696">Boolean</span></span>|  
|<span data-ttu-id="3e6ce-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-697">NULL_COLLATION</span></span>|<span data-ttu-id="3e6ce-698">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-698">Int32</span></span>|  
|<span data-ttu-id="3e6ce-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="3e6ce-700">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-700">Int64</span></span>|  
|<span data-ttu-id="3e6ce-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="3e6ce-701">COLUMN_NAME</span></span>|<span data-ttu-id="3e6ce-702">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-702">String</span></span>|  
|<span data-ttu-id="3e6ce-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-703">COLUMN_GUID</span></span>|<span data-ttu-id="3e6ce-704">GUID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-704">Guid</span></span>|  
|<span data-ttu-id="3e6ce-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="3e6ce-705">COLUMN_PROPID</span></span>|<span data-ttu-id="3e6ce-706">Int64</span><span class="sxs-lookup"><span data-stu-id="3e6ce-706">Int64</span></span>|  
|<span data-ttu-id="3e6ce-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-707">COLLATION</span></span>|<span data-ttu-id="3e6ce-708">Int16</span><span class="sxs-lookup"><span data-stu-id="3e6ce-708">Int16</span></span>|  
|<span data-ttu-id="3e6ce-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="3e6ce-709">CARDINALITY</span></span>|<span data-ttu-id="3e6ce-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="3e6ce-710">Decimal</span></span>|  
|<span data-ttu-id="3e6ce-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="3e6ce-711">PAGES</span></span>|<span data-ttu-id="3e6ce-712">Int32</span><span class="sxs-lookup"><span data-stu-id="3e6ce-712">Int32</span></span>|  
|<span data-ttu-id="3e6ce-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="3e6ce-713">FILTER_CONDITION</span></span>|<span data-ttu-id="3e6ce-714">String</span><span class="sxs-lookup"><span data-stu-id="3e6ce-714">String</span></span>|  
|<span data-ttu-id="3e6ce-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="3e6ce-715">INTEGRATED</span></span>|<span data-ttu-id="3e6ce-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="3e6ce-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e6ce-717">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e6ce-717">See also</span></span>

- [<span data-ttu-id="3e6ce-718">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="3e6ce-718">ADO.NET Overview</span></span>](ado-net-overview.md)
