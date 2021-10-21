---1.-Cómo obtenemos todos los nombres y correos de nuestros clientes canadienses para una campaña?
---Voy a suponer que una persona es canadiense si y solo si vive en Canada
---por que no veo un atributo de nacionalidad en ningún lado

select c.first_name, c.last_name, c.email
from customer c 
join address a using(address_id)
join city c2 using(city_id)
join country c3 using(country_id)
where c3.country ='Canada'



---2.-Qué cliente ha rentado más de nuestra sección de adultos?
---Hay 2 clientes con el mismo número

select concat(c.first_name, ' ', c.last_name) as name, count(r.rental_id) as count
from customer c 
join rental r using(customer_id)
join inventory i using (inventory_id)
join film f using (film_id)
where f.rating = 'NC-17'
group by 1
order by count desc
limit 2


---3.-Qué películas son las más rentadas en todas nuestras stores?


select title, store_id, count(rental_id) as count
from film f
join inventory i using(film_id)
join store s using (store_id)
join rental r using(inventory_id)
group by 1,2
order by count desc
limit 2

---4.- Cuál es nuestro revenue por store?

select s.store_id, sum(p.amount) as revenue
from payment p 
join rental r using(rental_id)
join inventory i using(inventory_id)
join store s using(store_id)
group by s.store_id 
order by store_id asc
