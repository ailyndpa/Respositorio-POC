/****** Script for SelectTopNRows command from SSMS  ******/
SELECT TOP (1000) f.Id,f.IataCode, f.NrFlight, f.Stda, f.StdaJul, f.Destination, p.Name, p.LastName, p.Bcbp, s.Letter, s.Number, t.RunwayId, t.OriginDate, t.ModifyDate, te.Description, te.Id
FROM [EasyPoc_DEV].[dbo].[Flights] as f
inner join [EasyPoc_DEV].[dbo].Passengers as p on p.FlightId = f.Id
inner join [EasyPoc_DEV].[dbo].Seats as s on s.FlightId = f.Id
inner join [EasyPoc_DEV].[dbo].Transactions as t on t.FlightId = f.Id
inner join [EasyPoc_DEV].[dbo].TransactionStates as te on te.id = t.TransactionStateId
where te.Id = 3